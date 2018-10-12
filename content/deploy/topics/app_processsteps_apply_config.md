# Apply Configuration {#app_processsteps_apply_config .reference}

This step runs a component process of the type Operational \(No Version Needed\) or Configuration Deployment.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes.

This step runs the specified component process if there is a difference in the configuration inventory of the resource and the configuration in the component process.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component**|Component that is used by the step; a step can affect a single component. All components that are associated with the application are available.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Maximum number of concurrent jobs**|The maximum number component instances to apply the new configuration to simultaneously. For example, if you set the maximum number of concurrent processes to 2, the server applies the configuration to only two instances of a component at a time, even if many instances of the component are installed. To apply the configuration to every component instance simultaneously, specify `-1`. To limit the number of components to change at once, as in rolling deployments, specify an integer.

The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

