# Setting server configuration security

Set the server configuration permissions to define what users can do with the HCL® UrbanCode™ Deploy server security, also referred to as system security. Typically, these permissions are granted to administrative roles.

The following server configuration permissions are available:

|Permission|Description|
|----------|-----------|
|Add Team Members|Add users to roles that have the same or fewer permissions than those of the granting user.|
|Edit Basic System Settings|Enables users to edit the options on the System Settings page. See, [Server settings](settings_system.md). This activity is written to the audit log.|
|Edit Network Settings|Grants users the permission to access the Network page and manage servers in a server cluster.|
|Manage Audit Log|Grants users the permission to manually cleanup the audit log, and configure automatic cleanup settings. If you have this permission but not the edit basic settings permission, you can edit the audit cleanup settings from the Audit Log page. This activity is written to the audit log.|
|Manage Auth Token Restrictions|Create, modify and delete token restrictions. See, [Restricting authentication tokens](security_token_restrict.md)|
|Manage Blueprint Designer Integrations|Grants users the permission to view and create Blueprint Designer integrations. These activities are written to the audit log.|
|Manage Diagnostics|Enable users to access the diagnostics information including the Rest Call Log, Java Thread dumps, and Metadata indexing. This activity is written to the audit log.|
|Manage Logging Settings|Grants users the permission to view the Logging page and edit the log4j configuration. This activity is written to the audit log.|
|Manage Notifications Schemes|Enable users to manage notification schemes used for notification emails. See, [Creating Notifications in a Notification Scheme](../../com.ibm.udeploy.doc/topics/notify_create.md). This activity is written to the audit log.|
|Manage Plug-ins|Grants users the permission to install new plug-ins; see [Installing plug-ins](settings_plugins.md). Install and delete activities are written to the audit log.|
|Manage Post Processing Scripts|Enable users to manage the post-processing scripts used by process steps. See, [The post-processing element](../../com.ibm.udeploy.reference.doc/topics/ref_create_postprocessing.md).|
|Manage Resource Roles|Grants users the permission to create and delete resource roles, which are created by some plug-ins. In most cases, you do not need to add or change resource roles because they are used internally.|
|Manage Security|Grants users the permission to create and edit version,inventory, and snapshot statuses.|
|Manage Statuses|Grants users the permission to manage security configuration, including roles, authentication realms, authorization realms, and tokens. Users without this permission cannot access or change the security functions. This activity is written to the audit log.|
|Manage System Properties|Grants users the permission to create and edit system properties. This activity is written to the audit log.|
|Read Artifact Set List|Enables agent relays to use component version replication by status. Assign a user with this permission to an authentication token intended for an agent relay.|
|Release Locks|Enables users to manually release any locks currently held. See, [Managing locks](settings_locks_managing.md). This action is written to the audit log.|
|View Audit Log|Grants users the permission to view the Audit Log page and download log files. This activity is written to the audit log.|
|View Basic System Settings|Enables users to view the options on the System Settings page. See, [Server settings](settings_system.md).|
|View Locks|Enables users to view any locks currently held. See, [Managing locks](settings_locks_managing.md). This action is written to the audit log.|
|View Network Settings|Grants users the permission to access the Network page.|
|View Output Log|Grants users the permission to view the Output Log page and download log files. This activity is written to the audit log.|

To add system security permissions to roles:

1.  Click **Settings** \> **Role Configuration** \> **selected role** \> **Server Configuration** to open the Permissions Granted to Role Members page for the target role.
2.  For each server configuration permission that you want to grant to the selected role, set each role to **On**.

**Parent topic:** [Roles and permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles.md)

