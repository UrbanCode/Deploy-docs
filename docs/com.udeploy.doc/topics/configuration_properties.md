# Viewing resource configuration inventories

You can view the configuration inventory for a component, which includes all properties that are associated with the component resource.

When you deploy a component, you store all the properties that are associated with the component, its application, and its environment on your deployment's resource target. From the resource tree, you can view which properties are active on the component resource.

1.  To view the resource tree, complete one of these steps: 
    -   To view the entire resource tree, click **Resources**.
    -   To view the resource tree for a specific application environment, click **Applications** \> **application name** \> **environment name**.
2.   Click the component's name. 
3.   From within the resource, click the **Inventory** tab. 
4.  In the Configuration Inventory pane, locate the property to examine.You might have to expand several levels to locate the properties. To view the properties that are associated with the component, expand both **Components** and the component itself.
5.   In the same row as the properties, click **View**. The Property Details dialog box is shown.
6.   Review the contents of the Property Details dialog box. The dialog box contains the following information:
    -   The versions of properties that are stored on the resource target
    -   The name and value of each stored property
7.   Click **Cancel** to return to the resource tree. 

If the resource target does not contain the correct version of the properties, you can configure a component process to update the properties. See [Component process types](comp_process_types.md#).

