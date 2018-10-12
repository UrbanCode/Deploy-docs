# Roles and permissions {#c_admin_roles .concept}

A number of roles are defined in the product that can be assigned to an user or group. Roles set boundaries on the release tasks that an user or group member can perform.

Roles are assigned to users and groups within the team context. Roles are not directly assigned to users and groups of users. Users or groups are assigned to a team with a specific role. The role assigned to a user is only for the team that the user is a member. A user can be a member of multiple teams and have a different role on each.

The interlocking concept of teams, roles, and permissions ensures that users have the appropriate permissions to perform their work and not affect processes outside of their assigned scope. The interaction of these three concepts provides the mechanisms to create an infrastructure that is secure and flexible.

The following table shows the available roles.

|Role|Permissions|
|----|-----------|
|Viewer| -   View pipelines

 |
|Developer| -   Manage templates
    -   Create templates
    -   Edit templates
    -   Delete templates
-   Pipelines
    -   Schedule pipelines
    -   Plans pipelines
-   Tasks
    -   Create tasks
    -   Edit tasks
    -   Remove tasks
-   Stories
    -   Create tasks
    -   Edit tasks
    -   Remove stories

 |
|Lead Developer| -   Pipelines
    -   Create pipelines
-   Applications
    -   Add applications to pipelines
    -   Edit pipeline applications
    -   Remove pipeline applications,
-   Environments
    -   Create pipelines environments
    -   Edit pipeline environments
    -   Remove pipeline environments
-   Deployment templates
    -   Create
    -   Edit
    -   Remove
-   Deployment plans
    -   Create deployment plans
    -   Modify deployment plans
    -   Delete deployment plans
    -   Schedule deployments in pipelines
-   Tasks
    -   Create tasks
    -   Modify tasks
    -   Delete task
-   Environments
    -   Create target environments
    -   Modify target environments
    -   Delete target environments
-   Releases
    -   Create releases
    -   Modify releases
    -   Delete releases
    -   Archive releases
-   Stories
    -   Create stories
    -   Modify stories
    -   Delete stories
    -   Archive stories
-   Members
    -   Create members
    -   Modify members
    -   Delete members
    -   Archive members
-   Assign roles
-   Teams
    -   Create teams
    -   Modify teams
-   Groups
    -   Create groups
    -   Modify groups
    -   Delete groups

 |
|Release participant|Create new tasks and run assigned tasks.-   Tasks
    -   Create tasks
    -   Modify tasks
    -   Delete task
-   Stories
    -   Create tasks
    -   Edit tasks
    -   Remove stories

|
|Release manager|-   CreateEditRemovePlansWithTemplates
-   SchedulePlansInPipelines
-   CreateEditRemoveTasks
-   CreateEditReleases
-   ArchiveReleases
-   CreateEditRemoveUserStories
-   ModifyCalendarSettings

Schedule releases, and run releases and calendar events using pre-defined templates.|
|Lead release manager| -   CreateEditRemovePlanTemplates
-   CreateEditRemovePlansWithTemplates
-   CreateEditRemovePlansWithoutTemplates
-   SchedulePlansInPipelines
-   CreateEditRemoveTasks
-   ChangeTaskTargetEnvironments
-   CreateEditReleases
-   ArchiveReleases
-   CreateEditRemoveUserStories
-   AssignRoles
-   ApproveProtectedEnvironments
-   AddEditRemoveMembers
-   CreateTeams
-   RemoveTeams
-   EditTeams
-   CreateEditRemoveGroups
-   ModifyCalendarSettings

 |
|Team Administrator| -   AssignRoles
-   AddEditRemoveMembers
-   CreateTeams
-   RemoveTeams
-   EditTeams
-   CreateEditRemoveGroups

 **Note:** Members assigned the Lead Developer and Lead Release Manager roles can also perform the tasks assigned to the team administrator.

 |
|Product administrator| -   ModifySettings
-   AddEditRemoveMembers
-   AssignRoles
-   CreateEditRemoveIntegrations
-   CreateTeams, RemoveTeams
-   EditTeams
-   CreateEditRemoveGroups
-   ManageLocalUsers

 |

Global administrator vs team administrator....

**Parent topic:** [Security](../topics/c_node_security.md)

