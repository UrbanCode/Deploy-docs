# Examples of post-processing scripts {#comp_postprocess_examples .concept}

Post-processing scripts are written in JavaScript™.

Post-processing scripts must set the Status property to specify the status of the script. The script can specify any value for the Status property. For example, to specify that the script was a success, run the following command in the post-processing script:

```
properties.put("Status","Success");
```

## Writing to the log { .section}

You can write to the output log for the process with the following command:

```
commandOut.print("hello");
```

## Checking the result of a step { .section}

The post-processing script can examine the step's output log and run commands based on the result. In the following code fragment, `scanner.register()` registers the strings error at line and the value is with a regular expression engine, then runs commands if those strings are found. After all strings are registered, it calls `scanner.scan()` on the step's output log line by line.

```
     properties.put("Status", "Success");

     //
     // Evaluate the built-in exitCode property, which indicates the exit code
     // of the script called by the plug-in step. Typically, if the value of
     // the exitCode property is non-zero, the plug-in step failed.
     //
     if (properties.get("exitCode") != 0) {
          properties.put("Status", "Failure");
     }
     else {

          //
          // Register a scanner to search for the text "error at line" in the log.
          // The first argument is a regular expression.
          //
          // The second argument, an inline function, is invoked once for
          // every line in the log output that matches the pattern. The "lineNumber"
          // variable contains the line number where the match occurred, and the
          // "line" variable is the full text of the line.
          //
          scanner.register("(?i)ERROR at line",  function(lineNumber, line) {

              //
              // In this case, we build up an "Error" property which
              // contains the text of all errors that are found. We find every
              // line starting with "error at line" and add it to this list.
              //
              errors.put("Errors", errorString);


              //
              // If a line starting with "error at line" is found, the step has
              // failed, so we set the special "Status" property to "Failure",
              // indicating to the UrbanCode Deploy server that the step should
              // be marked as a failure.
              //
              properties.put("Status", "Failure");
          });
         
          //
          // Multiple searches can be registered with the scanner. We add a
          // second search to look for some interesting text to set as an output
          // property.
          //
          // For example, if there is a line "The value is BLUE", then we end up
          // with an output property, "Value", with a value of "BLUE".
          //
          scanner.register("The value is", function(lineNumber, line) {
              var value = line.replace("The value is ", "");
              properties.put("Value", value);
          });
         
          scanner.scan();


          //
          // Convert the collected list of error strings into a single string and
          // set that as an output property.
          //
          var errors = properties.get("Error");
          if (errors == null) {
              errors = new java.util.ArrayList();
              properties.put("Error", errors);
          }
          properties.put("Error", errors.toString());
     }

```

## Retrieving a property from a previous step { .section}

The following scripts assume two steps that are in the same process. The post-processing script for the first step creates two output properties, which are named Status and Step1Prop:

```
if (properties.get("exitCode")==0)
  { properties.put("Status","Success"); }
else
  { properties.put("Status","Failure"); }

properties.put("Step1Prop","value1");
```

Then, a second step can access those properties. For example, if the first step was named `Step1` and specified the output properties Status and Step1Prop, you might create a Shell step with the following code to access those properties:

```
echo Properties of previous step:
echo "${p:Step1/Status}"
echo "${p:Step1/Step1Prop}"

```

The second step can also use those properties in its post-processing script. For example, the following post-processing script includes the Status property of the previous step in a property for the second step:

```
{ 
properties.put("Step2Prop","New property");
properties.put("Status","OK"); 
properties.put("StatusOfPreviousStep","${p:Step1/Status}"); 
}
```

## Passing a value from one step to another { .section}

Passing a value from one step to another involves a few general steps:

1.  In the first step, store the value in a place where the post-processing script can access it. You can store the value by writing it to the log file for the step. For example, if you are using a Shell step, you can write the value and a unique key to the log with an `echo` command:

    ```
    echo "myvalue=1234"
    ```

    As a result, the log for the step shows the key and value:

    ```
    myvalue=12345
    ```

2.  In the post-processing script for the step, use the scanner object to scan the log for the key. Then, assign the value to an output parameter. The following example script searches the output log for the key `myvalue=` and then stores the value in the output property `myOutputValue`:

    ```
    var exit = properties.get('exitCode');
    
    scanner.register("myvalue=", function(lineNumber, line) {
         var value=line.replace("myvalue=","");
         properties.put("myOutputValue",value);
    });
    
    if (exit == 0) {
        properties.put('Status', 'Success');
    }
    else {
         properties.put('Status', 'Failure');
    }
    
    scanner.scan();
    ```

3.  In future steps, refer to the output parameter of the first step. For example, if the first step is named `SetMyValue`, future steps can refer to the property with the following code:

    ```
    ${p:SetMyValue/myOutputValue}
    ```


**Parent topic:** [Post-processing scripts](../topics/comp_postProcess.md)

