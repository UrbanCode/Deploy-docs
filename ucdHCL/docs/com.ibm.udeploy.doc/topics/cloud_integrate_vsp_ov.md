# Connecting to clouds through HCL UrbanCode Deploy

The HCL® UrbanCode™ Deploy server can use virtual system patterns from cloud systems such as IBM® Cloud Orchestrator to create dynamic environments.

You must have a user account on a cloud system. This account must have permission to create script packages, to read information about virtual system patterns, IP groups, cloud groups, and environment profiles, and to create and delete virtual environments. See the documentation for your cloud system for more information about setting up permissions. For example, for IBM PureApplication® System, see [https://www.ibm.com/support/knowledgecenter/SSCRSX\_2.1.0/doc/iwd/aac\_user\_permissions.dita](https://www.ibm.com/support/knowledgecenter/SSCRSX_2.1.0/doc/iwd/aac_user_permissions.dita).

For this type of cloud integration, the following cloud systems are supported:

-   IBM Cloud Orchestrator version 2.4 or later
-   IBM SmartCloud® Orchestrator versions 2.2 and 2.3
-   IBM PureApplication System version 1.0 or later
-   IBM Workload Deployer version 3.1.0.6 or later

Within these cloud systems, you can provision the virtual resources in environment profiles or in cloud groups. You can also assign the virtual resources to IP groups, but only when you assign the resources to an environment profile first. For more information, see [Creating environments](app_environment_create.md). You can also use virtual images with no more than one virtual network card. HCL UrbanCode Deploy does not support selecting different flavors of virtual resources or virtual nodes that have a multiplicity greater than 1.

To connect to OpenStack and OpenStack-based clouds, SoftLayer®, Amazon Elastic Compute Cloud, VMware vCenter, or Microsoft™ Azure, see [Connecting to clouds through the blueprint designer](../../com.ibm.edt.doc/topics/security_cloud_connection.md).

**Note:** If you installed a FIPS-compliant server as described in [Installing the server in interactive mode](../../com.ibm.udeploy.install.doc/topics/server_install_interactive.md), the HCL UrbanCode Deploy server cannot integrate with cloud systems through virtual system patterns. Your JVM connects to only FIPS 140-2 certified IBM providers. The blueprint design server can still connect to clouds through OpenStack Heat.

1.  Configure the cloud system to install agents automatically. See [Configuring virtual system pattern-based clouds](../../com.ibm.udeploy.install.doc/topics/cloud_configure.md).
2.  Create a connection to a cloud system. 

    1.  Click **Resources** \> **Cloud Connections** and then click **New Connection**.
    2.  In the **Name** field, specify a name for the connection.
    3.  In the **Management Console** field, specify the host name of the cloud system.
    4.  In the **Username** field, specify the user name of an account that has permission to request cloud resources. The server stores this user name and password and uses it to request cloud resources when you use this cloud connection.
    5.  In the **Password** field, specify the password for the user account.
    6.  In the **Description** field, specify a description for the connection.
    7.  In the **Teams** field, specify the teams that have access to this connection.
    8.  Set the timeout for cloud requests by opening the file installed.properties on the server and specifying the cloud.requestTimeout property. This property specifies the timeout in seconds. The default value is 7200 seconds, or two hours.
    9.  Click **Save**.
    The new cloud connection is included in the **Cloud Connections** pane.


Model environments for this cloud. See [Modeling environments for clouds that use virtual system patterns](../../com.ibm.edt.doc/topics/blueprint_edit_clouds_vsp.md).

**Parent topic:** [Overview of integrations](../topics/integrat_ov.md)

