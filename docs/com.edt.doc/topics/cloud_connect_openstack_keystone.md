# Connecting to OpenStack-based clouds with Keystone authentication

To use the accounts on an OpenStack Keystone server for authentication to the OpenStack cloud connection, create an authentication realm that points to the Keystone server. Then, configure security for that authentication realm.

-   Configure the images for use with the blueprint designer. See [Configuring OpenStack images](cloud_connect_openstack_images.md).
-   Extend the Heat engine that is associated with the OpenStack server. You must use an OpenStack Heat engine that is installed with the OpenStack server, not an engine that you install with HCL® UrbanCode™ Deploy. See [Installing the blueprint design server](../../com.udeploy.install.doc/topics/install_server_bds.md).
-   Install the blueprint design server. See [Installing the blueprint design server](../../com.udeploy.install.doc/topics/install_server_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.udeploy.doc/topics/ucdp_integrate.md#).
-   Ensure that the blueprint design server can connect to the cloud. You can verify the connection path with the curl or telnet commands. For example, make sure that no firewall, proxy, or security settings prevent communication between the blueprint design server and the cloud.

The following diagram shows a typical topology for this scenario. The blueprint design server connects to the OpenStack-based cloud and the OpenStack Heat engine. The engine is extended for use with the blueprint design server. The blueprint design server also connects to the license server and the Keystone identity service. The blueprint design server retrieves authentication information from this Keystone identity service.

![A topology that includes the blueprint design server, an OpenStack-based cloud, an OpenStack Heat engine, and a Keystone server](../images/cloud_connect_openstack_keystone_a.gif)

1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.   Create an authentication realm that points to the Keystone server. See [Creating OpenStack identity service authentication realms for the blueprint designer](../../com.udeploy.admin.doc/topics/security_realms_openstack.md). 
3.  Import the users from that authentication realm. The blueprint designer creates the following artifacts:
    -   The blueprint designer creates a user in the authentication realm for each user on the Keystone server.
    -   The blueprint designer creates a cloud connection on the **Clouds** tab. \(Click **Settings** \> **Clouds**.\)
    -   The blueprint designer creates a cloud project for each tenant or project on the cloud. If your OpenStack identity service uses Identity API v3, the domain for each project is specified.
4.  Add the cloud projects to teams.
5.  Add one or more users from that authentication realm to a team and assign those users one or more roles.The users on the team have access to the cloud projects that are associated with that team.
6.   Make sure that the team roles include the appropriate permissions for those users, such as creating and editing blueprints. 
7.   If the cloud uses SSL security, configure SSL security on the blueprint design server. See [Configuring SSL security for OpenStack clouds](cloud_connect_ssl.md). 

Users can log in to the blueprint designer with the accounts on the Keystone server. At the top of the page, users can select the cloud connection, cloud project, and region. When they edit blueprints, the palette shows resources that are available from the cloud that the user account is associated with.

**Note:** When a user logs in to the blueprint designer, the blueprint designer matches the user name to the authentication realms, starting at the top of the list. If the user name is present in more than one authentication realm, the blueprint designer uses the listing in the highest authentication realm.

**Parent topic:** [Connecting to OpenStack and OpenStack-based clouds](../../com.edt.doc/topics/cloud_connect_openstack.md)

