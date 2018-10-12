# Creating component-type resources {#resources_createComponent .task}

Component-type resources represent the components that are deployed to target environments.

Component-type resources are created on the Resource Tree page. The Resource Tree page displays resources in a hierarchical tree structure. Each row on the Resource Tree page represents a resource and has a context-sensitive **Action** menu that is associated with it. The available actions depend on whether the resource represents an agent, agent pool, component, or an organizational group.

1.   Open the Resource Tree page. In addition to the Resource Tree page, resources can be displayed in several ways, such as by adding resources to an environment.
2.   To create a resource, open the **Action** menu for the resource where you want to create the resource and click **Add Component**. New resources are inserted below the selected resource. Components can be added below agents, agent pools, and other components.
3.   From the **Component** list, select the component to associate with the resource. 
4.   In the **Name** field, enter a name for the resource. By default, the resource name is the same as the component name.
5.   Perform one of the following steps: 
    1.   If you want the team that manages the resource's parent to manage this resource, select the **Inherit Teams From Parent** check box. The **Inherit Teams From Parent** check box is selected by default.
    2.   If you do not want the parent team to manage this resource, clear the **Inherit Teams From Parent** check box. You can add a team by using the **Teams** action, then selecting a team.
6.   If you added the component resource below an agent, agent pool, or another component, the option to define default user impersonation credentials is available. See [Defining default user impersonation credentials](resources_impersonation.md#) for information about setting impersonation credentials. 
7.   If the component associated with the resource has any resource properties defined for it, they are displayed in the Role Properties area where you can set their value. If you change the default value, the **Reset to Default** action is displayed in the **Actions** field. 
8.   Save your work. 

For information about using resources in applications, see [Mapping resources and components to environments](app_environment_mapping.md#).

**Parent topic:** [Modifying the resource tree](../topics/resource_tree_modify.md)

