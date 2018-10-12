# Run Process for Each Version {#app_processsteps_run_process_version .reference}

Use this step to run the specified process once for each version of the specified component.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes.

This step runs the specified component process for all selected versions, whether or not each component version is in the inventory. By contrast, the [Install Component](app_processsteps_install.md) step runs the component process only for component versions that are not already in the inventory.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component**|Component that is used by the step; a step can affect a single component. All components that are associated with the application are available.|
|**Component Process**|The component process to run.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run, per component. This setting limits the number of processes that run simultaneously on each component. For example, if you set the maximum number of concurrent processes to 2, the server accesses only two instances of a component at a time, even if many instances of the component are installed. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Run on First Online Resource Only**|Instead of being run by all agents that are mapped to the environment, the step runs only on the first online agent that the server identifies. The mechanism that is used to identify the "first" agent is database-dependent, and thus indeterminate. If no agents are online, the server skips the step and marks its status as "Not Mapped." This setting may cause the environment to become noncompliant or to provide unexpected results, because only one agent runs the process, even if many agents are mapped to the environment.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

