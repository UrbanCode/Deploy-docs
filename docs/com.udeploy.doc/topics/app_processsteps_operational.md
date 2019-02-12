# Operational component processes

Runs the specified operational \(no version needed\) component process.

You can add operational component processes to application processes if the operational component processes do not require a component version. Operational component processes that do not require versions are listed in the step palette under **Component Process Steps**. To add an operational \(no version needed\) component process to an application process, drag the folder that represents the component to the application process and then select the operation process to run. To run an operational \(with version\) component process, use the [Run Process for Each Version](app_processsteps_run_process_version.md) step.

To learn about the different types of component processes, see [Component process types](comp_process_types.md).

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Limit to Tag**|Run the process only on the versions with the specified tag.|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run, per component. This setting limits the number of processes that run simultaneously. For example, if you set the maximum number of concurrent processes to 2, the process runs on only two instances of a component at a time, even if many instances of the component are installed. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Run on First Online Resource Only**|Instead of being run by all agents that are mapped to the environment, the step runs only on the first online agent that the server identifies. The mechanism that is used to identify the "first" agent is database-dependent, and thus indeterminate. If no agents are online, the server skips the step and marks its status as "Not Mapped." This setting may cause the environment to become noncompliant or to provide unexpected results, because only one agent runs the process, even if many agents are mapped to the environment.|
|**Precondition**|A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|
|**Run If Components Change**|When this check box is selected, this step runs only if an agent resource that is mapped to this component has other component resource mappings whose inventories are changed by the process. When you select this check box, you can select components and specify whether the step runs on all resources for the component that contains this process, or only on resources that include both the component for this process and one of the selected components that was changed by this process.**Resource Selection Mode** options:

-   To run the operational process only on resources that have had their inventory updated for one of the selected components, select **Only resources where selected components are changed**. For example, when you have a component that contains some operational processes, for example, "Restart HTTP Server", you can add the operational process to the application process and you can select this option to run only on machines where you have deployed changes to web sites being hosted.
-   To run the operational process wherever the component defining the process is added to any agents in the environment, select **All resources mapped to this process's component**. For example, if after you deploy changes to a web site you want to restart a load balancer that is on a different machine than the web site, you can select this option to run the operational process wherever the "Load Balancer" component that contains the "Restart Load Balancer" operational process is mapped.

|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

