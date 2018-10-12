# Rollback Multiple Components {#concept_xsp_w3w_mt .concept}

Use this step to roll back multiple component versions to versions in a snapshot or to versions that were deployed when the process began. The multiple components are based on component tags or resource tags.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes, including application processes that are associated with application templates.

In most cases, to switch to different component versions, you deploy the new versions over the existing versions. If necessary, you can run the uninstall process for the components first.

However, you can also use the Rollback Component step to automate the process of switching to a previous component version. This step has two options:

-   **Remove Undesired Incremental Versions**: This option removes versions that are not in a specified snapshot. See [Rolling back to a snapshot](app_process_deploy_rollback.md).
-   **Replace with Last Deployed**: This option rolls back components that fail to deploy. See [Uninstalling components with an application process](app_process_deploy_uninstall.md#).

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component Tag**|A user-defined component tag that is used to select components. Only components with the specified tag are modified by this step.|
|**Component Process**|The component process to run. In most cases, select a component process that uninstalls the component.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Remove Versions With Status**|Restricts the components that are affected by the step. Only components with the selected status are affected. Available statuses: Active refers to components that are currently deployed.|
|**Rollback Type**|Determines the type of rollback. If you specify `Remove Undesired Incremental Versions`, the server runs the uninstall process for each version that is not in the specified snapshot. See [Rolling back to a snapshot](app_process_deploy_rollback.md). If you specify `Replace with Last Deployed`, the server runs the specified process on the version that was installed when the process began. See [Uninstalling components with an application process](app_process_deploy_uninstall.md#).|
|**Maximum number of concurrent components**|The maximum number of components to roll back at one time. For example, if you specify 5, this step rolls back five components at a time on all agents to which the components are installed. To run this step on all components at the same time, specify `-1`. To limit the number of components to access at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run, per component. This setting limits the number of processes that run simultaneously to roll back each component. For example, if you set the maximum number of concurrent processes to 2, only two instances of a component are rolled back at a time, even if there are many instances of the component. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition**|A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

