# Default properties

Many default properties are available for use while a process runs. These properties provide information about the process and the elements that are involved in the process, such as applications, components, and resources.

To see the properties that are available to a process, run the process. When the process is finished, go to the **Properties** tab of the process request. This tab lists all the properties that are available to the process.

The following table lists properties that are automatically available to processes and the types of processes that can access each property.

|Property|Description|Process types|
|--------|-----------|-------------|
|agent.id|The unique ID of the agent.|Generic processes and component processes|
|agent.name|The name of the agent.|Generic processes and component processes|
|application.id|The unique ID of the application.|Application processes, component processes|
|application.name|The name of the application.|Application processes, component processes|
|applicationProcess.id|The unique ID of the application process.|Application processes|
|applicationProcess.name|The name of the application process.|Application processes|
|component.id|The unique ID of the component.|Application processes, component processes|
|component.name|The name of the component.|Application processes, component processes|
|componentProcess.defaultWorkDir|The default working directory for the component. The value of this property is equivalent to $\{p:resource/work.dir\}/$\{p:component.name\}, where $\{p:resource/work.dir\} is the default working directory for the agent and $\{p:component.name\} is the component name.|Component processes|
|componentProcess.id|The ID of the component process.|Component processes|
|componentProcess.name|The name of the component process.|Component processes|
|currentVersion.id|The ID of the component version that is used in the process.|Component processes|
|currentVersion.name|The name of the component version that is used in the process.|Component processes|
|currentVersion.type|Whether the component version is a full version or incremental version.|Component processes|
|environment.id|The unique ID of the environment.|Application processes, component processes|
|environment.name|The name of the environment.|Application processes, component processes|
|finalStatus|Whether the process succeeded \(`Success`\) or failed \(`Failure`\).|Application processes, generic processes, component processes|
|parentRequest.id|The ID of the parent process.|Application processes, component processes|
|request.id|The unique ID of the process request.|Application processes, generic processes, component processes|
|request.user.displayName|The name of the user that requested the process.|Application processes, generic processes, component processes|
|request.user.id|The unique ID of the user that requested the process.|Application processes, generic processes, component processes|
|request.user.name|The user name of the user that requested the process.|Application processes, generic processes, component processes|
|resource|The unique ID of the resource that the process runs on.|Generic processes|
|resource.id|The unique ID of the resource that the process runs on.|Generic processes, component processes|
|resource.name|The name of the resource that the process runs on.|Generic processes, component processes|
|resource.parent.path|The parent of the resource that the process runs on|Generic processes, component processes|
|resource.path|The location of the resource in the resource tree.|Generic processes, component processes|
|resource/system/work.dir|The working directory on the agent resource.|Generic processes|
|resource/work.dir|The working directory on the agent resource.|Generic processes|
|server.url|The URL of the HCL® UrbanCode™ Deploy server.|Application processes, component processes, generic processes|
|snapshot.name|The name of the snapshot that was used to specify the component versions. This snapshot is sent only when a snapshot is being deployed.|Application processes|
|snapshot.id|The unique ID of the snapshot that was used to specify the component versions. This snapshot is sent only when a snapshot is being deployed.|Application processes|
|version.id|The unique ID of the component version.|The built-in version of this property is available only to component processes that are not of the Operation\(no version required\) type.|
|version.name|The name of the component version.|The built-in version of this property is available only to component processes that are not of the Operation\(no version required\) type.|
|working.dir|The working directory for the process.|Generic processes|

Steps in component processes also have access to the output properties of previous steps, as in this table:

|Property|Description|
|--------|-----------|
|`stepName/exitCode`|The exit code of the component process step. 0 indicates success; any other value indicates failure.|
|`stepName/LOI`|The lines of interest \(LOIs\) are lines of code that the postprocessing script finds in the step's output log. See [The post-processing element](../../com.udeploy.reference.doc/topics/ref_create_postprocessing.md).|
|`stepName/Status`|Whether the step succeeded \(`Success`\) or failed \(`Failure`\).|
|`stepName/outputProperty`|An output property from a previous step. See [Examples of post-processing scripts](comp_postprocess_examples.md).|

For example, if a prior step in the process is named `step1`, later steps can access properties such as `step1/exitCode`. If the step `step1` creates an output property that is named `output1`, later steps can access that property with the code `step1/output1`.

**Parent topic:** [Properties](../topics/ud_properties_overview.md)

