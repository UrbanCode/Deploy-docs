# Adding tags to objects {#addingtags_tsk .task}

Add tags to objects to simplify object management, to improve object sorting, and to facilitate task execution by tag.

1.   Navigate to the object. You can apply tags to applications, components, and resources. You can apply tags to resources in your current resource tree or to resources in a resource template. See [Creating resource templates](resources_templates_create.md#).
2.   Hover the mouse pointer over the object, and click the **Add Tag** icon ![](../images/add_tag_icon.gif) that is displayed. A window opens where you can select or create a tag.
3.  In the new window, take one of these actions: 
    -   Expand the list, and select a tag.
    -   Click **Create Tag**. Type a tag name, and select a tag color. Optionally, type a tag description. Click **Save**.

-   To organize a list of objects by tag, click **Flat list**. Select **By Tag** to organize the objects into a hierarchical list that is sorted by tag.
-   To tag multiple objects at a time or to remove tags from multiple objects at a time, first select the check boxes to left of the objects. Then, click **Actions**, and select **Add Tag** or **Remove Tag**.
-   To view all objects that have the same tag, in the tags field at the top of any list of objects, type the name of a tag, and then press Enter. Only the objects that are tagged with the exact text that you type in the **Tags** field are displayed. If a tag name contains spaces, surround the name with double quotation marks when you type it in the **Tags** field.
-   To select all objects that have the same tag, first filter the objects as explained in the previous section. Then, click **Select All**, and select **Matching Filter**.
-   To quickly assign a process to a specific agent, first tag the agent. Then, click the top-level **Processes** tab, click a process, and then click **Set**. Filter the agents as explained in the previous section, select the agent, and then click **OK**.
-   To limit the installation of multiple components in application process to certain components or resources, first tag the components or resources. In the application process, click and drag the **Install multiple components** step to the process editor. In that step, use the **Component Tag** field to deploy the components that have a specific tag and the **Limit to Tag** field to use resources with a specified tag.
-   To automatically import versions of a component by using any one of several agents, tag the agents. From the **Components** tab, click **Create Component**. Click **Import new component versions using any agent with the specified tag.**, and in the **Agent Tag for Version Imports** list, select the tag.

**Parent topic:** [Tags](../topics/tags_ch.md)

