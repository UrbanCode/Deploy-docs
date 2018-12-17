# Permission reference

This table lists the permissions on the server that you can assign to roles.

The following table lists the product areas with their available permissions. Because of the large number of edit subpermissions, they are provided in a separate column.

|Product area|Available permissions|Subpermissions|
|------------|---------------------|--------------|
|Agent| -   **Execute on agents**: run processes on the agent
-   **View Agents**: access agents in the UI but cannot modify them
-   **Edit**: modify and delete agents

 |Edit-   **Add to Agent Pool**: assign agents to agent pools
-   **Create Resources**: create agent-type resources
-   **Delete**: delete agents
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Impersonation**: set up user impersonation for agents
-   **Manage Properties**: create and modify agent properties
-   **Manage Teams**: assign agents to teams
-   **Manage Version Imports**: import component versions with the agent
-   **Upgrade Agents**: upgrade agents

|
|Agent pool| -   **Create Agent Pools**: create agent pools
-   **View Agent Pools**: access agent pools in the UI but cannot modify them
-   **Edit**: modify and delete agent pools

 |Edit-   **Create Resources**: create agent pool resources
-   **Delete**: delete agent pools
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Pool Members**: change the agents that are in a pool
-   **Manage Teams**: assign agent pools to teams

|
|Agent relay| -   **View Agent Relays**: see the agent relays that are listed on the **Resources** tab

 |Edit-   **Delete**: delete agent relays
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Teams**: assign agent relays to teams

|
|Application| -   **View Applications**: access applications in the UI but cannot modify them
-   **Create**: create applications
-   **Edit**: modify and delete applications

 |Create-   **Create Applications**: create applications without using a template
-   **Create Applications From Template**: create applications by using templates to define their attributes

Edit-   **Delete**: delete applications
-   **Delete Snapshot**: delete snapshot
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Blueprints**: create and modify blueprints
-   **Manage Components**: add and remove components
-   **Manage Environments**: create and modify environments
-   **Manage Processes**: create application processes
-   **Manage Properties**: create and modify application properties
-   **Manage Snapshots**: create and modify snapshots
-   **Manage Teams**: assign teams to applications
-   **Run Component Processes**: run processes that are defined for components that are attached to the application

|
|Application template| -   **Create Application Templates**
-   **View Application Templates**
-   **Edit**

 |Edit-   **Delete**: delete applications
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Blueprints**: create and modify blueprints
-   **Manage Component Tags**: add and remove component tags
-   **Manage Environment Templages**: create and modify environment templates
-   **Manage Processes**: create application processes
-   **Manage Properties**: create and modify application properties
-   **Manage Teams**: assign teams to applications

|
|Cloud connection| -   **Create Cloud Connections**: create connections
-   **View Cloud Connections**: access connections in the UI but cannot modify them
-   **Edit**: modify and delete connections

 |Edit-   **Delete**: delete cloud connections
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Teams**: assign teams to cloud connections

|
|Component| -   **View Components**: access components in the UI but cannot modify them
-   **Create**: create components
-   **Edit**: modify and delete components

 |Create-   **Create Components**: create components without using a template
-   **Create Components From Template**: create components by using templates to define their attributes

Edit-   **Delete**: delete components
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Edit Components**: create and modify components
-   **Manage Configuration Templates**: create configuration templates
-   **Manage Processes**: create component processes
-   **Manage Properties**: create component properties
-   **Manage Teams**: assign teams to components
-   **Manage Versions**: import component versions

|
|Component template| -   **Create Component Templates**: create component templates
-   **View Component Templates**: access component templates in the UI but cannot modify them
-   **Edit**: modify and delete component templates

 |Edit-   **Delete**: delete component templates
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Processes**: create and modify component template processes
-   **Manage Properties**: create and modify component template properties
-   **Manage Teams**: assign teams to component templates

|
|Environment| -   **Execute on Environments**: run parent applications
-   **View Environments**: access environments in the UI but not modify them
-   **Create**: create environments
-   **Edit**: modify and delete environments

 |Create-   **Create Environments**: create environments without using a template
-   **Create Enviornments From Template**: create environments by using templates to define their attributes

Edit-   **Delete**: delete environments
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Approval Processes**: create and modify approvals and notifications
-   **Manage Base Resources**: add base resources to environments
-   **Manage Properties**: create and modify environment properties
-   **Manage Teams**: assign teams to environments

|
|Environment template| -   **Create Environment Templates**
-   **View Environment Templates**
-   **Edit**

 |Edit-   **Delete**: delete applications
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Approval Processes**: create modify approvals and notifications
-   **Manage Properties**: create and modify environment properties
-   **Manage Teams**: assign teams to environments

|
|Process| -   **Create Processes**: create processes
-   **Execute Processes**: run processes
-   **View Processes**: access process definitions in the UI but cannot modify them
-   **Edit**: modify and delete processes

 |Edit-   **Delete**: delete generic processes
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Properties**: create and modify generic process properties
-   **Manage Teams**: assign teams to generic processes

|
|Resource| -   **Create Resources**: create resources
-   **Execute on Resources**: Run processes on agent resources
-   **View Resources**: access resources in the UI but cannot modify them
-   **Edit**: modify and delete resources

 |Edit-   **Delete**: delete resources
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Children**: create, modify, and delete resource hierarchies
-   **Manage Impersonation**: set up user impersonation for agent and agent pool resources
-   **Manage Properties**: create and modify resource properties
-   **Manage Teams**: assign teams to resources
-   **Map to Environments**: assign resources to application environments

|
|Resource template| -   **Create Resource Templates**: create resource templates
-   **View Resource Templates**: access resource templates in the UI but cannot modify them
-   **Edit**: modify and delete resource templates

 |Edit-   **Delete**: delete resource templates
-   **Edit Basic Settings**: edit configuration settings on the Basic Settings panel
-   **Manage Resources**: create, modify, and delete resource hierarchies
-   **Manage Teams**: assign teams to resource templates

|

The page of permissions also includes **Server Configuration** and **Web UI** sections. These permissions affect how users can modify security settings on the server and which pages in the server user interface they can see.

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

|Permission|Description|
|----------|-----------|
|Applications Tab|Access to the Applications tab; see [Applications](../../com.ibm.udeploy.doc/topics/applications_ch.md)|
|Components Tab|Access to the Components tab; see [Components](../../com.ibm.udeploy.doc/topics/comp_ch.md)|
|Configuration Tab|Access to the Configuration tab; see [Creating, setting, and editing properties](../../com.ibm.udeploy.doc/topics/resources_properties.md)|
|Dashboard Tab|Access to the Dashboard tab.|
|Deployment Calendar Tab|Access to the Calendar tab; see [Scheduling deployments](../../com.ibm.udeploy.doc/topics/schedules_ch.md)|
|Processes Tab|Access to the Processes tab; see [Generic processes](../../com.ibm.udeploy.doc/topics/genProcess_ch.md)|
|Reports Tab|Access to the Reports tab; see [Reporting](../../com.ibm.udeploy.doc/topics/reports_ch.md)|
|Resources Tab|Access to the Resources tab; see [Resources](../../com.ibm.udeploy.doc/topics/resources_ch.md)|
|Settings Tab|Access to the Settings tab; see [Server settings and configuration](../../com.ibm.udeploy.doc/topics/settings_ch.md)|
|Work Items Tab|Access to the Work Items tab; see [Work items](../../com.ibm.udeploy.doc/topics/app_approvals_workitems.md)|

**Parent topic:** [Roles and permissions](../../com.ibm.udeploy.admin.doc/topics/security_roles.md)

