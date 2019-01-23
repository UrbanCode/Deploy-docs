# create\_file.groovy

The create\_file.groovy file contains the Groovy script that runs the step's command.

Groovy is a dynamic scripting language \(similar to Python, Ruby, and Perl\) for the Java™ platform. Most Java code is also syntactically valid Groovy, which makes Groovy popular with Java programmers. Groovy provides native support for regular expressions.

The first lines of the script create a properties object, `props`. Then it attempts to load the properties from the file that is sent from the server \(specified by the `${PLUGIN_OUTPUT_PROPS}` variable\). If it can load the file, it populates `props`; otherwise, it throws an exception.

```
final def workDir = new File('.').canonicalFile
final def props = new Properties();
final def inputPropsFile = new File(args[0]);
try {
inputPropsStream = new FileInputStream(inputPropsFile);
props.load(inputPropsStream);
}
catch (IOException e) {
throw new RuntimeException(e);
}

```

To run the command \(create a file\), the script uses the properties that are defined by the step itself. The script retrieves the three properties from `props` and creates corresponding local variables.

Next, the script creates a file with a name specified by `fileName`, and tests the `overwrite` Boolean variable. If a file with the same name exists and `overwrite` is false, the script ends \(fails\) with an exit code of 1. Exit codes can be examined during post-processing.

Otherwise, the file is written with the content of `contents`. A message is written to the output log, and the exit code is set to 0 \(success\).

```
final def fileName = props['file']
final def overwrite = props['overwrite']?.toBoolean()
final def contents = props['contents']?:''

try {
def file = new File(fileName).canonicalFile
if (file.exists() && !overwrite) {
println "File $file already exists!"
System.exit 1
}
else {
file.write(contents)
println "Successfully ${overwrite?'replaced':'created'} file 
$file with contents:"
println contents
}
}
catch (Exception e) {
println "Error creating file $file: ${e.message}"
System.exit(1)
}

System.exit(0)

```

**Parent topic:** [Step commands](../../com.ibm.udeploy.reference.doc/topics/ref_example_step_commands.md)

