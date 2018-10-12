# Creating agent-type and agent pool-type resources {#resources_createAgent .task}

Agent-type and agent pool-type resources represent the computers where components are deployed.

Resources are created on the Resources page. The Resources page displays resources in a hierarchical tree structure. Each row on the Resources page represents a resource and has a context-sensitive **Action** menu that is associated with it. The available actions depend on whether the resource represents an agent, agent pool, component, or an organizational group.

1.   Open the Resource Tree page. In addition to the Resource Tree page, resources can be displayed in several ways, such as by adding resources to an environment.
2.   To create a resource, open the **Action** menu for the resource where you want to create the resource and click **Add Agent** or **Add Agent Pool**. New resources are inserted below the selected resource. Agents and agent pools can be added below group-type resources.
3.   From the Agent list, select the agent or agent pool that you want to associate with the resource. 
4.   In the **Name** field, enter a name for the resource. By default, the resource name is the same as the agent or agent pool name.
5.   Perform one of the following steps: 
    1.   If you want the team that manages the resource's parent to manage this resource, select the **Inherit Teams From Parent** check box. The **Inherit Teams From Parent** check box is selected by default.
    2.   If you do not want the parent team to manage this resource, clear the **Inherit Teams From Parent** check box. You can add a team by using the **Teams** action, then selecting a team.
6.   Define default user impersonation credentials. For information about setting impersonation credentials, see [Defining default user impersonation credentials](resources_impersonation.md#).
7.   Save your work. 

For information about using resources in applications, see [Mapping resources and components to environments](app_environment_mapping.md#)

**Parent topic:** [Modifying the resource tree](../topics/resource_tree_modify.md)

