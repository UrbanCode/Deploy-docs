# Security teams

Users and groups on the server are assigned roles when they are added to teams.

Teams provide two important functions. First, a team provides the mechanism to assign roles to users. When a user is assigned a role, all permissions that are granted to the role are automatically granted to the user, but only for objects that the team has access to. Second, teams secure objects such as applications, components, and environments. When a team is attached to an object, only team members with the appropriate permissions can interact with the affected resource.

The System Team that comes with HCL® UrbanCode™ Deploy has all permissions granted for all Standard security types for its Administrator role.

-   **[Creating teams](../../com.udeploy.admin.doc/topics/security_teams_create.md)**  
Create teams to add users to and for managing access to resources on the server.
-   **[Assigning users to teams](../../com.udeploy.admin.doc/topics/security_teams_users.md)**  
Assign users to teams so that users can be assigned to roles and work with objects that are associated with the teams.
-   **[Mapping teams to objects](../../com.udeploy.admin.doc/topics/security_teams_mapping.md)**  
In addition to assigning a team to an object \(such as a component or application\), when you create the object, you can use the Teams page on the server to map teams to objects.
-   **[Assigning teams directly to items](../../com.udeploy.admin.doc/topics/security_teams_resources.md)**  
You can assign a team to an object \(such as components or applications\) when you create the object.

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

