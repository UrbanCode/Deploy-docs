# Troubleshooting security and permissions {#trouble_permissions .concept}

To troubleshoot permissions, look carefully at the roles and teams of the user and the teams of the object that the user is trying to access.

 User cannot access a page on the server
 :   If a user cannot see pages on the server, make sure that the user's role has the permission to see that page. Open the user's role, go to the Web UI category, and specify the pages that the user can access. See [Creating roles and assigning permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles_create.md).

  User cannot access an object
 :   If a user cannot access an object, such as an application or environment, check the following things:

    -   Ensure that the object is part of a team and that the user is a member of the same team. You can add an object to a team only if you are a member of that team.
    -   Ensure that the user has a role on that team, and that the role includes permission to access the object.
    -   If the object has a security type other than the standard security type for that object, make sure that the role includes permissions for that security type.
    -   Ensure that the user has access to the related pages on the server, such as the **Applications** tab or **Components** tab.
    -   If the user can create an object but cannot set configuration options for it, make sure that the user's role has the Edit Basic Settings and Manage Teams permissions for that type, because otherwise the options for creating the object are limited.

 **Parent topic:** [Troubleshooting the IBM UrbanCode Deploy server and agents](../topics/trouble_serveragents_ov.md)

