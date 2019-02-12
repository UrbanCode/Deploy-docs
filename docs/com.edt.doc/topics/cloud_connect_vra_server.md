# Connecting the blueprint design server to VMware vRealize Automation

To integrate the blueprint design server with VMware vRealize Automation Enterprise, you must first configure the integration.

-   Obtain a Heat engine and an OpenStack Keystone server. The engine version must match the version of the Keystone server. In most cases for deploying to non-OpenStack clouds, install a Heat engine and Keystone server through HCL® UrbanCode™ Deploy. See [Installing an engine in silent mode](../../com.udeploy.install.doc/topics/install_engine_silent.md) or [Installing an engine in interactive mode](../../com.udeploy.install.doc/topics/install_engine_interactive.md).
-   Create a functional user account on the Keystone server. This user account must be a member of the administrative tenant on the Keystone server. If you use the Keystone server that was supplied with the engine, you can use the default administrative tenant credentials. The Keystone server's default administrative tenant user name is `admin` and the default password is `openstack1`.
-   To integrate IBM UrbanCode Deploy blueprint designer with VMware vRealize Automation v7 and 7.1, you must have these elements:

    -   A VMware vRealize Automation URL
    -   A VMware vRealize Automation tenant ID, for example vsphere.local
    -   A working VMware vRealize Automation account
    **Important:** The HCL UrbanCode Deploy version 6.2.2 and later blueprint designer requires the vRealize Automation account to have one of these two roles:

    -   Tenant administrator
    -   Business group manager
-   Install the blueprint design server. See [Installing the blueprint design server](../../com.udeploy.install.doc/topics/install_server_bds.md).
-   Configure an authentication realm for the blueprint design server. You can import users from a variety of sources, including LDAP servers, Keystone identity services, the HCL UrbanCode Deploy server, or from the internal authentication realm. See [Creating authentication realms for the blueprint designer](../../com.udeploy.admin.doc/topics/security_realms_create.md#).
-   Ensure that the blueprint design server can connect to the cloud. You can verify the connection path with the curl or telnet commands. For example, make sure that no firewall, proxy, or security settings prevent communication between the blueprint design server and the cloud.

When you integrate with a VMware vRealize Automation Enterprise server, you can create blueprints that model deployments to the vCenter servers that are connected to the vRealize Automation server.

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.   Create a connection to the cloud: 
    1.   Click **Settings** \> **Clouds**. 
    2.   Click **Add New Connection**. 
    3.   Specify a name for the cloud connection. 
    4.   In the **Type** list, select **VMware vRealize**. 
    5.   Click **Save**. 
3.   To create a cloud project, see [Creating cloud projects for the blueprint designer](security_projects.md). 
4.   Add the cloud project to a team. 
5.   Add users to the team and to one or more roles on the team. These users can come from any authentication realm, including LDAP servers, Keystone identity services, or from the internal authentication realm.
6.   Make sure that the team roles include the appropriate permissions for those users, such as creating and editing blueprints. 

You can log in to the blueprint designer as a user from that team. At the top of the page, you can select the vRealize Automation cloud connection and cloud project to use. When you edit blueprints, the palette shows resources that are available to your vRealize Automation account, and you can provision blueprints to the vCenter clouds that you access through vRealize Automation.

**Parent topic:** [Connecting to VMware vRealize Automation v7 and v7.1](../../com.edt.doc/topics/cloud_connect_vra.md)

