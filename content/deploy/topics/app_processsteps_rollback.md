# Rollback Component {#app_processsteps_rollback .reference}

Use this process step to roll back a component version to the version in a snapshot or to the version that was deployed when the process began.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes.

For a video demonstration of rolling back components, see [Rollback Scenarios in IBM UrbanCode™ Deploy](https://www.youtube.com/watch?v=8hH25vJ2f3E).

In most cases, to switch to a different version of a component, you deploy the new version over the existing version. If necessary, you can run the uninstall process for the component first.

However, you can also use the **Rollback Component** step to automate the process of switching to a previous component version. This step has two options:

-   **Remove Undesired Incremental Versions**: This option removes versions that are not in a specified snapshot. See [Rolling back to a snapshot](app_process_deploy_rollback.md).
-   **Replace with Last Deployed**: This option rolls back components that fail to deploy. See [Uninstalling components with an application process](app_process_deploy_uninstall.md#).

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component**|Component that is used by the step; a step can affect a single component. All components that are associated with the application are available. If you want to roll back another component, add another rollback step to the process or use the [Rollback Multiple Components](app_process_rollback_multi.md) step.|
|**Remove Versions with Status**|Restricts the component versions that are affected by the step. Only versions with the selected status are affected. By default, the status `Active` refers to versions that are currently deployed.|
|**Component Process**|The component process to run. In most cases, select a component process that uninstalls the component.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Rollback type**|Determines the type of rollback. If you specify `Remove Undesired Incremental Versions`, the server runs the uninstall process for each version that is not in the specified snapshot. See [Rolling back to a snapshot](app_process_deploy_rollback.md). If you specify `Replace with Last Deployed`, the server runs the specified process on the version that was installed when the process began. See [Uninstalling components with an application process](app_process_deploy_uninstall.md#).|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run. This setting limits the number of processes that run simultaneously. For example, if you set the maximum number of concurrent processes to 2, only two instances of a component are rolled back at a time, even if there are many instances of the component. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

