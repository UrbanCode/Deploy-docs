# The `command` element

Steps are run by starting the scripting tool or interpreter that is specified by the `<command>` element. The `<command>` element's `program` attribute defines the location of the tool that runs the command.

It bears repeating that the tool must be on the host and the agent that starts the tool must have access to it. In the following example, the location of the tool that runs the command \(the Java™ scripting tool Groovy in this instance\) is defined.

```
<command program='${GROOVY_HOME}/bin/groovy'>

```

The actual command and any parameters it requires are passed to the tool by the `<command>` element's `<arg>` child element. Any number of `<arg>` elements can be used. The `<arg>` element has several attributes:

|Attribute|Description|
|---------|-----------|
|`<value>` |Specifies a parameter that is passed to the tool. Format is tool-specific; must be enclosed by quotation marks.|
|`<path>` |Path to files or classes that are required by the tool. Must be enclosed by quotation marks.|
|`<file>` |Specifies the path to any files or classes that are required by the tool. Format is tool-specific; must be enclosed by quotation marks.|

Because `<arg>` elements are processed in the order they are defined, ensured the order conforms to the order that is expected by the tool.

```

<command program='${GROOVY_HOME}/bin/groovy'>
  <arg value='-cp' />
  <arg path='classes:${sdkJar}:lib/commons-codec.jar:
    lib/activation-1.1.1.jar:
    lib/commons-logging.jar:lib/httpclient-cache.jar:
    lib/httpclient.jar:lib/httpcore.jar:
    lib/httpmime.jar:lib/javamail-1.4.1.jar' />
  <arg file='registerInstancesWithLB.groovy' />
  <arg file='${PLUGIN_INPUT_PROPS}' />
  <arg file='${PLUGIN_OUTPUT_PROPS}' />
</command>

```

The `<arg file='${PLUGIN_INPUT_PROPS}'/>` specifies the location of the tool-supplied properties file. The `<arg file='${PLUGIN_OUTPUT_PROPS}'/>` specifies the location of the output file for the step-generated properties.

Note: new lines are not supported by the `<arg>` element and are shown in this example only for presentation.

**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

