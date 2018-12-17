# Connecting the blueprint design server to Google Cloud Platform

To connect the blueprint design server to Google Cloud Platform, map the Google Cloud Platform account information to a functional ID. Then, assign that functional ID to a team.

-   Create a project in your Google Cloud Platform account. You must enable the Google Compute Engine API for the project and store all of the Compute Engine resources in the project. See [Enable and disable APIs](https://support.google.com/cloud/answer/6158841?hl=en).
-   Obtain a Heat engine and an OpenStack Keystone server. The engine version must match the version of the Keystone server. In most cases for deploying to non-OpenStack clouds, install a Heat engine and Keystone server through HCL® UrbanCode™ Deploy. See [Installing an engine in silent mode](../../com.ibm.udeploy.install.doc/topics/install_engine_silent.md) or [Installing an engine in interactive mode](../../com.ibm.udeploy.install.doc/topics/install_engine_interactive.md).
-   Create a functional user account on the Keystone server. This user account must be a member of the administrative tenant on the Keystone server. If you use the Keystone server that was supplied with the engine, you can use the default administrative tenant credentials. The Keystone server's default administrative tenant user name is `admin` and the default password is `openstack1`. Later, you associate the Google Cloud account information with this functional ID. With this account, users can authenticate to Google Cloud.
-   Install the blueprint design server. See [Installing the blueprint design server](../../com.ibm.udeploy.install.doc/topics/install_server_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md#).
-   Configure an authentication realm for the blueprint design server. You can import users from a variety of sources, including LDAP servers, Keystone identity services, the HCL UrbanCode Deploy server, or from the internal authentication realm. See [Creating authentication realms for the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_realms_create.md#).
-   Ensure that the blueprint design server can connect to the cloud. You can verify the connection path with the curl or telnet commands. For example, make sure that no firewall, proxy, or security settings prevent communication between the blueprint design server and the cloud.

The blueprint design server and engine connect to Google Cloud. For authentication information, the blueprint design server connects to the Keystone identity service and optionally to an LDAP server.

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Create a connection to the cloud: 
    1.  Click **Settings** \> **Clouds**.
    2.   Click **Add New Connection**. 
    3.  Specify a name for the cloud connection.
    4.  In the **Type** list, select **Google Cloud Platform**. 
    5.  Click **Save**.
3.   To create a cloud project, see [Creating cloud projects for the blueprint designer](security_projects.md). 
4.  Add the cloud project to a team.See [Configuring blueprint design server teams](../../com.ibm.udeploy.admin.doc/topics/security_teams_bds.md#).
5.   Add users to the team and to one or more roles on the team. These users can come from any authentication realm, including LDAP servers, Keystone identity services, or from the internal authentication realm.
6.   Make sure that the team roles include the appropriate permissions for those users, such as creating and editing blueprints. 

You can log in to the blueprint designer as a user from that team. At the top of the page, you can select the Google Cloud cloud connection and region to use. When you edit blueprints, the palette shows resources that are available to your Google Cloud project, and you can provision blueprints to Google Cloud.

**Parent topic:** [Connecting to Google Cloud Platform](../../com.ibm.edt.doc/topics/cloud_connect_google_cloud.md)

