# Managing environment inventory and compliance

You can allow the server to manage the environment inventory and compliance automatically, or you can manage the environment inventory and compliance with steps in an application process.

The inventory for an environment shows the component versions that are intended to be deployed to an environment. The compliance level shows the component versions that are successfully deployed to that environment. For more information about the concepts of inventory and compliance, see [Environment inventory and compliance](env_compliance.md).

When you create application processes, you can allow the server to manage the environment inventory and compliance automatically, or you can manage the inventory and compliance yourself. If the inventory management is automatic, the server automatically updates the inventory and compliance for each environment. When you run an application process, the server adds the selected component versions to the environment inventory. Similarly, when component processes run, the server updates the inventory to show which component versions were deployed and which component versions were not.

For example, assume that an application process deploys one component version, but the component deployment process for another component version fails. In this case, the server sets the environment inventory to include the two component versions. The server also sets the compliance to include only the component version that was deployed.

As an alternative, you can manage the environment inventory and compliance manually. In this case, you add steps that make specific changes to the inventory and compliance.

1.  In the settings for the application process, set **Inventory Management** to **Advanced**.
2.  In the application process, add steps to install, uninstall, or configure component versions as usual.
3.   Add the **Component Inventory Update** utility step, and then specify the properties for the step as described in [Inventory Update](app_process_inventory_update.md). Specifically, specify the component to update the inventory for and the changes to make to the inventory and compliance. You can add as many Component Inventory Update steps to the process as you need.

    For example, to add a component version to the inventory and set the compliance to active, specify the following properties: select the component; from the **Action** list, select **Add Desired Inventory**; and from the **Status** list, select **Active**.

    **Note:** The Component Inventory Update and Snapshot Inventory Update steps are available only in application processes that have **Inventory Management** set to **Advanced**.

4.   If you use snapshots in application processes, add the **Snapshot Inventory Update** utility step. Specify whether to add a snapshot version to or remove a snapshot version from the inventory, as described in [Snapshot Inventory Update](app_process_snap_update.md). 

**Parent topic:** [Environment inventory and compliance](../topics/env_compliance.md)

