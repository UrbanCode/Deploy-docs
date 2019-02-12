# The `post-processing` element

When a plug-in step's `<command>` element finishes processing, the step's mandatory `<post-processing>` element runs.

The `<post-processing>` element sets the step's output properties \(step name/property name, see [Output properties](../../com.udeploy.doc/topics/output_properties.md)\) and provides error handling. The `<post-processing>` element can contain any valid JavaScript™ 1.7 script \(unlike the `<command>` element, `<post-processing>` scripts must be written in JavaScript 1.7\). Users can also provide their own scripts when they define the step in the HCL® UrbanCode™ Deploy editor; see [Post-processing scripts](../../com.udeploy.doc/topics/comp_postProcess.md).

Post-processing scripts have access to the following objects:

-   The properties object is an instance of the class java.util.Properties. This variable has several special properties: `exitCode` contains the process exit code and `Status` contains the step's status. A `Status` value of `Success` means that the step completed successfully.

    This object is the same Java™ properties object that the step returns. Therefore, you can use the properties object in the post-processing script to change the output properties of the step. For example, to add an output property that is named `OutputProp1` with the value `value1`, add the following code to the post-processing script:

    ```
    properties.put("OutputProp1","value1");
    ```

    Then, the precondition scripts of other steps can access this property. See [Process step preconditions](../../com.udeploy.doc/topics/comp_process_step_precondition.md).

    For more information about this object, see the Java reference for java.util.Properties.

-   The scanner object can scan the step's output log \(scanning occurs on the agent\) and run commands based on the results. scanner has several public methods:
    -   `register(String regex, Function script)` registers a function to be called when the regular expression is matched. The function accepts two parameters: the first parameter is the line number that matched the regular expression, and the second parameter is the line of text that matched that expression.
    -   `addLOI(Integer lineNumber)` adds a line to the lines of interest list, which are highlighted in the Log Viewer. The scanner adds all matching lines to this list automatically, but you can add other lines by calling this method.
    -   `getLinesOfInterest()` returns a java.util.List of lines of interest; can be used to remove lines.
    -   `scan()` scans the log. Call this method after you have registered all regular expressions with register\(\). If you do not call this method, the registered matchers do not run.
-   The commandOut object is an instance of the class java.io.PrintStream. You can use this object to write to the log, as in the following example:

    ```
    commandOut.println("Log message.");
    ```

    For more information about this object, see the Java reference for java.io.PrintStream.


Post-processing scripts must set the Status property to specify the status of the script. The script can specify any value for the Status property. For example, to specify that the script was a success, run the following command in the post-processing script:

```
properties.put("Status","Success");
```

You can use a post-processing script to set output properties that can be used in other steps in the same process, which enables complex workflows. In a post-processing \(or precondition\) script, refer to prior step output properties this way:

```
properties.get("stepName/propName")
```

For example, to set a property named `myProp` whose value is included in the output log, enter this script:

```
var exit = properties.get('exitCode');
 scanner.register("^myProp:", function(lineNumber, line) {     
      properties.put('myProp', line.substring(7))
 });
 if (exit == 0) {
     properties.put('Status', 'Success');
 }
 else{
    properties.put('Status', 'Failure');
 }
```

In instances other than post-processing and precondition scripts, refer to prior step output properties this way:

```
${p:stepName/propName}
```

The script that is defined in the `<post-processing>` element is the step's default behavior. Users can also provide their own script, overriding the default behavior, when they define the step in the process editor. See [Editing processes](../../com.udeploy.doc/topics/comp_workflow_edit.md).

**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

