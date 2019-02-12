# Component process types

Different types of component processes deploy, configure, or uninstall component versions.

In most cases, you run component processes by adding them to application processes. However, you can also run component processes directly. For more information, see [Running component processes](comp_process_run.md).

The Deployment and Operational \(With Version\) process types require a component version. If you do not specify a component version, the process does not run. In this case, the process is shown in the log with this message: No Version Selected. You can access the component version name with the $\{p:version.name\} property. See [Referring to properties](ud_properties_using.md#).

The other component process types do not use a specific component version; they run the same way regardless of the inventory of the target resource. Therefore, version-specific properties such as the $\{p:version.name\} property are not available.

You use the following component process types:

-   **Deployment**

    This type of component process deploys the specified component version to the target resource. It is the most common type of component process. If no component version is specified, the process does not run. For example, if the deployment manifest or snapshot does not contain a version of the specified component, the process does not run.

    After the process runs, it updates the component inventory to include the component version, even if the process failed. If the process finishes, it updates both the component inventory and the configuration inventory, which contains all the properties for that component and its related elements. To view the updated properties, see [Viewing resource configuration inventories](configuration_properties.md#).

    In most cases, this type of component process includes the Download Artifacts step, which downloads the component version artifacts to the target resource. Then, the process includes steps that install or configure the component version.

    The most common way to run a deployment component process is to add it to an application process. In an application process, add the Install Component step, and then select the deployment component process.

-   **Configuration Deployment**

    This type of component process applies a configuration inventory to a deployed component.

    After the process runs, it updates the resource configuration inventory to contain updated properties. It does not change the environment or component version inventories.

    For example, this type of process might use configuration templates to create configuration files, as described in [Creating configuration files in component processes](comp_tasks_config_create.md). As another example, this type of process can update an application server with the most recent component properties, environment properties, and application properties. In this case, the process updates the configuration on the application server without reinstalling the component.

    To include this type of process in an application process, add the Apply Configuration step, and select the configuration deployment process.

-   **Uninstall**

    This type of component process removes the component version from the target resource. It also removes the component version from the environment inventory. It does not modify the configuration inventory.

    To use this type of process in an application process, add the Uninstall Component step, and select the Uninstall component process.

    This type of process can uninstall all the component versions in the inventory or only the specified versions. When you add a component with this component process to an application process, you specify the **Uninstall Type** field. The **All Existing** option removes all the versions of this component that are in the inventory. The **All Selected For Process** option removes only the versions that you specify when you start the application process.

-   **Operational \(With Version\)**

    This type of process does not add or remove artifacts from the inventory; it runs steps on a currently deployed component. For example, this type of process can start or stop a service or change the properties on a deployed component.

    By default, this type of process always runs when you include it in an application process, but you can restrict it to run only when certain components change.

    To use this type of process in an application process, add a step that can call this type of process. For example, the Run Process for Each Version and Install Component steps can call this type of process.

    Running this process step does not update the component's properties on the target resource.

-   **Operational \(No Version Needed\)**

    This type of process is the same as the Operational \(With Version\) type, except that this type does not use a component version.

    Each process of this type is listed as an available application process step, and you can add its step to call the process. You can also add a step that can call this type of process, such as the Apply Configuration step, to use this type of component process in an application process.


**Parent topic:** [Component processes](../topics/intro_component_processes.md)

