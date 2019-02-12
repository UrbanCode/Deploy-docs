# Inventory Update

This step updates the inventory and compliance for the environment.

**Restriction:** The Component Inventory Update and Snapshot Inventory Update steps are available only in application processes that have **Inventory Management** set to **Advanced**. See [Managing environment inventory and compliance](inventory_manage_app.md). This step is available only to processes that have the **Inventory Management** check box set to **Advanced**.

|Field|Description|
|-----|-----------|
|**Component**|Component that is used by the step; a step can affect a single component. All components that are associated with the application are available.|
|**Limit to Tag**|The user-defined resource tag that determines which resource runs the process. Only a resource with this tag, or a resource that has a parent with this tag, runs the process. See [Adding tags to objects](addingtags_tsk.md#).|
|**Action**|Select **Add Desired Inventory** to add component versions to the inventory. Select **Remove Desired Inventory** to remove component versions from the inventory.|

**Parent topic:** [Process steps: Reference](../topics/app_processSteps.md)

