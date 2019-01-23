# Install Component

This step installs the selected component with one of the processes that are defined for the component.

**Tip:** 

Applications, components, and generic processes share some process steps. This step applies only to application processes.

This step runs the specified component process for all selected component versions, except the component versions that are already in the inventory. By contrast, the [Run Process for Each Version](app_processsteps_run_process_version.md) step runs the process for each component version, whether or not each component version is in the inventory.

It is up to you to select an appropriate component process to run. In most cases, select a component process of the Deployment type. If you select a different type of component process, you might get results that you do not expect. The server runs whatever component process you select, even if that process does not install the component. For example, if you select a component process of the Uninstall type, the Install Component step runs that component process as usual. Then, the component process uninstalls the component and removes the component from the inventory.

This step can install multiple incremental versions of the same component. To do this, use a single Install Component step in the application process. Then, when you run the application process, select multiple incremental versions to deploy. The incremental versions are deployed in the order that you select them in the Run Process window. To deploy the incremental versions in a specific order, you can also create a snapshot, add the component versions to the snapshot in the order that you want to deploy them, and run the application process with the snapshot.

|Field|Description|
|-----|-----------|
|**Name**|A name for the step. Other process steps can refer to this step by this name.|
|**Component**| Component that is used by the step; a step can affect a single component. All components that are associated with the application are available. To install another component, add another install step to the process.|
|**Use Versions Without Status**|Restricts the components that can be used by the step. Components with the selected status are ignored. Available statuses: Active means ignore components that are currently deployed.|
|**Component Process**|The component process to run.|
|**Limit to Tag**|User-defined roles can be used in processes; see [Adding tags to objects](addingtags_tsk.md#).|
|**Maximum number of concurrent processes**|The maximum number of concurrent processes to run. This setting limits the number of processes that run simultaneously to deploy the component. For example, if you set the maximum number of concurrent processes to 2, only two instances of the component are installed at a time, even if many instances of the component are mapped to agents. To run an unlimited number of concurrent processes, specify `-1`. To limit the number of processes to run at once, as in rolling deployments, specify an integer.The server attempts to resolve the value to an integer. If the value does not resolve to an integer, then the `-1` value is used by default. You can use a property in this field, as long as the property resolves to an integer.

**Note:** The maximum number of component processes that can run concurrently is limited by the hardware that hosts the agent.

|
|**Fail Fast**|If this check box is selected, the step does not start more processes after one process fails.|
|**Precondition** |A JavaScript 1.7 script that defines a condition that must exist before the step can run. The condition must resolve to `true` or `false`. In the script, do not use the `${p:component.myProperty}` notation. For example, to check the value of a component property in a component process, use `properties.get("myProperty") == "myValue"`. See [Property contexts](ud_properties_context.md#) for information about property access.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

