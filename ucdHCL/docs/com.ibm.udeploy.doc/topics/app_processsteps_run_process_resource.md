# Run Generic Process for Each Affected Resource

Runs the specified generic process on each resource that is affected by the application process.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies to application processes, component processes, and generic processes. This step applies to application processes that are associated with application templates.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Process**|The generic process to run.|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run at the same time. For example, if you set the maximum number of concurrent processes to 2, the generic process runs on only two resources at a time. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|
|Other properties|After you select a generic process, the properties for that process are listed. You can set values here to pass to the process.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

