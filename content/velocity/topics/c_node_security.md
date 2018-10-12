# Security {#c_node_security .concept}

The UrbanCode Velocity security model is organization- and team-based. The organization is the base element; teams belong to organizations. Team members manage releases, events, and deployments. Administrators manage teams and assign users to them.

The team-based security model means that teams manage releases, reports, pipelines, events, and run deployments. Only team members can create or modify team-managed objects. Users can be assigned to more than one team. Users are identified by email address. The UrbanCode Velocity administrator manages the security system and manages teams and users.

After UrbanCode Velocity is [integrated with IBM UrbanCode Deploy](t_integration_UCD.md#), UrbanCode Deploy teams and applications can be imported into UrbanCode Velocity. When a team is imported, all team members are imported. Users are identified by email address. Administrators can also create users.

-   **[Roles and permissions](../topics/c_admin_roles.md)**  
A number of roles are defined in the product that can be assigned to an user or group. Roles set boundaries on the release tasks that an user or group member can perform.
-   **[Managing users](../topics/t_admin_authentication.md)**  
Use the User authentication settings page to manage user authentication.
-   **[Managing user groups](../topics/cr_security_groups.md)**  
You can combine users into groups. When you grant permissions to the group, you simultaneously grant them to the group members. When you assign a group to a team, all group members are simultaneously assigned to the team.
-   **[Managing teams](../topics/cr_security_teams.md)**  
To prepare a team, you create the team and then add users or user groups to it. After you add users, you assign permissions to them.
-   **[Managing user permissions](../topics/cr_security_permissions.md)**  
Permissions define the scope of user actions. Administrators assign permissions when they add users to teams. Permissions are granted to individual users or user groups. Users can have different permissions for different teams.
-   **[Managing UrbanCode Deploy teams](../topics/cr_security_UCDteams.md)**  
When an UrbanCode Deploy team is imported, in addition to the roster of team members, all applications that are managed by the team are also imported. Imported applications can be used in any deployment that is managed by the team.

**Parent topic:** [Administration](../topics/c_node_admin.md)

