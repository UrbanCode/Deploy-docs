# Run Operational Process for Multiple Components {#app_processsteps_operational .reference}

Runs the operational \(no version needed\) process for multiple components.

You can add multiple operational component processes to application processes if the operational component processes do not require a component version. To learn about the different types of component processes, see [Component process types](comp_process_types.md). To run a single operational process, see [Operational component processes](app_processsteps_operational.md#).

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes, including application processes that are associated with application templates.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component Tag**|A user-defined component tag that is used to select components. Only components with the specified tag are modified by this step.|
|**Component Process**|A process for the components that contain the selected tag. Only components that contain the process will run. Only one process can be selected per step.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Maximum number of concurrent components**|The maximum number of components on which to run processes at one time. For example, if you specify 5, this step runs processes on five components at a time. To run this step on all components at the same time, specify `-1`. To limit the number of components to access at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run, per component. This setting limits the number of processes that run simultaneously. For example, if you set the maximum number of concurrent processes to 2, the process runs on only two instances of a component at a time, even if many instances of the component are installed. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Run on First Online Resource Only**|Instead of being run by all agents that are mapped to the environment, the step runs only on the first online agent that the server identifies. The mechanism that is used to identify the "first" agent is database-dependent, and thus indeterminate. If no agents are online, the server skips the step and marks its status as "Not Mapped." This setting may cause the environment to become noncompliant or to provide unexpected results, because only one agent runs the process, even if many agents are mapped to the environment.|
|**Precondition**|A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|
|**Run If Component with Tag Changes**| To run this step only if another step in the application process changes the inventory of a component, select this option.

 If you select a component tag, for this step to run, a component that contains that tag must have an inventory change. If you do not select a component tag, any inventory change that is caused by the application process causes this step to run.

 **Note:** Do not select the same component tag that you selected in the **Component Tag** list.

 Select an option in the **Resource Selection Mode** list to control the agent resources that this step runs on.

 -   To run the step on only resources where the inventory of other components changes, select **Only resources where component with selected tag is changed**. For example, you might have a component that contains some operational processes, such as "Restart HTTP Server." If you add the operational process to the application process, you can select this option to run only on machines where you are deploying changes to websites that are hosted.
-   To run the operational process on all possible resources, select **All resources mapped to this process's component**. For example, if you deploy changes to a website, you might want to restart a load balancer that is on a different machine than the website. You can select this option to run the operational process wherever the "Load Balancer" component that contains the "Restart Load Balancer" operational process is mapped.

 |

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

