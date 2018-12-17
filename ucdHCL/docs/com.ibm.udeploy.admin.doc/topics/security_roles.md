# Roles and permissions

A role is a list of permissions that users have on the HCL® UrbanCode™ Deploy server. These permissions include the ability to create, edit, and delete objects, such as applications, environments, and components. The permission also includes the parts of the server interface that users can access.

When you assign users to a role, they get all permissions that are granted to the role. However, these permissions apply only to the team on which the user has the role. For example, if a user has the Developer role on team A, that user has the role permissions on the environments, applications, and components that are assigned to team A. The user does not have any permissions on the environments, applications, and components that are assigned to team B unless you assign that user a role on team B.

You can assign permissions to a user only by giving that user a role on a team. You cannot assign a user to a role without also putting that user on a team. Similarly, you cannot assign a user to a team without giving that user a role on the team.

Typically, the permissions that are granted to a role define a particular activity that a user might do, such as running deployments. Users can be assigned to more than one role, and users can have different roles on different teams. You decide the number of roles and their permissions that you assign to users. Initially, HCL UrbanCode Deploy provides one role, the Administrator role, which has all possible permissions granted to it.

**Note:** If a role grants the Create permission for some object type, such as components, it is important that the role also grant the Edit Basic Settings and Manage Teams permissions for that type. Otherwise, the options for creating the object are limited.

The Create permission is different from other permission types. The create type is not scoped to a specific resource but is more broadly scoped. Team members with a create-type permission can create resources of the related type without team members first being attached to a specific resource. To continue the environment example, users with the create environment permission can create environments even if their team is not attached to a specific environment.

Most objects have the create, view, and edit permissions that most object types. Environments and processes have an execute permission. This permission controls the ability to run processes.

-   **[Creating roles and assigning permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles_create.md)**  
You can create roles on the server and assign permissions to them.
-   **[Setting server configuration security](../../com.ibm.udeploy.admin.doc/topics/security_system.md)**  
Set the server configuration permissions to define what users can do with the HCL UrbanCode Deploy server security, also referred to as system security. Typically, these permissions are granted to administrative roles.
-   **[Permission reference](../../com.ibm.udeploy.admin.doc/topics/security_roles_permission_ref.md)**  
This table lists the permissions on the server that you can assign to roles.
-   **[Permissions reference for using application templates](../../com.ibm.udeploy.admin.doc/topics/app_template_ref.md)**  
Permissions for roles that create applications from templates.

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

