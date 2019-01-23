# Creating groups

Resource groups organize resources into logical groupings.

Resources are created on the Resource Tree page. The Resource Tree page displays resources in a hierarchical tree structure. Each row represents a resource and has a context-sensitive **Action** menu that is associated with it. The available actions depend on whether the resource represents an agent, agent pool, component, or organizational group.

1.   Open the Resource Tree page. In addition to the Resource Tree page, resources can be displayed in several ways, such as by adding resources to an environment.
2.   Perform one of the following steps: 

    1.   To create a top-level group, click **Create Top-Level Group**. The top-level groups are ordered alphabetically.
    2.   To create a resource group beneath an existing resource, display the **Action** menu for the resource, and then use the **Add Group** command. 
    The Create Resource dialog box is displayed.

3.  Enter a name and an optional description.
4.   To specify criteria that are used to automatically populate the resource, select the **Include Agents Automatically** check box. 

    **Note:** To automatically include agents, you must be a member of either the agent's team or the system team, such as the admin user. You must specify the team that will access the group, and that group must have access to the agent that you describe. You cannot assign the system team to the group.

    Select **Name** or **Property**, and then select a filter criterion from the list. The available criteria are listed:

    -   **Equals** 
    -   **Doesn't Equal** 
    -   **Contains** 
    -   **Doesn't Contain** 
    -   **Matches Regex** \(match a regular expression\)
    You can set more than one condition. If any agent-type resource in the filtered group satisfies the condition, it is preserved, otherwise it is removed. If agents that satisfy the condition exist, but they are not in the group, agent-type resources are created and added to the group.

5.   If you added the group beneath an existing resource, perform one of the following steps: 
    1.   If you want the team that manages the resource's parent to manage this resource, select the **Inherit Teams From Parent** check box. The **Inherit Teams From Parent** check box is selected by default.
    2.   If you do not want the parent team to manage this resource, clear the **Inherit Teams From Parent** check box. You can add a team by using the **Teams** action, then selecting a team.
6.  If you added the resource below an agent, agent pool, or a component, the option to define default user impersonation credentials is available. See [Defining default user impersonation credentials](resources_impersonation.md#) for information about setting impersonation credentials.
7.  Save your work.

For information about using resources in applications, see [Mapping resources and components to environments](app_environment_mapping.md#).

**Parent topic:** [Modifying the resource tree](../topics/resource_tree_modify.md)

