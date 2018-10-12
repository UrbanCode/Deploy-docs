# Uninstall Multiple Components {#app_processsteps_uninstall .reference}

Use this step to uninstall multiple components that are based on component tags or resource tags.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes, including application processes that are associated with application templates.

It is up to you to select an appropriate component process to run. In most cases, select a component process of the Uninstall type. If you select a different type of component process, you might get results that you do not expect. The server runs whatever component process you select, even if that process does not uninstall the component. For example, if you select a component process of the Deployment type, the Uninstall Component step runs that component process as usual. Then, the component process deploys the component and adds the component to the inventory.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component Tag**|A user-defined component tag that is used to select components. Only components with the specified tag are modified by this step.|
|**Component Process**|The component process to run.|
|**Limit to Resource Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Remove Versions With Status**|Restricts the components that are affected by the step. Only components with the selected status are affected. Available statuses: `Active` refers to components that are currently deployed.|
|**Maximum number of concurrent components**|The maximum number of components to uninstall at one time. For example, if you specify 5, this step runs the uninstall component processes for five components at a time. To run this step on all components at the same time, specify `-1`. To limit the number of components to access at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run, per component. This setting limits the number of processes that run simultaneously to uninstall each component. For example, if you set the maximum number of concurrent processes to 2, only two instances of a component are uninstalled at a time, even if many instances of the component are currently installed. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|
|**Uninstall Type**|The **All Existing** option removes all the versions of this component that are in the inventory. The **All Selected For Process** option removes only the versions that you specify when you start the application process.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

