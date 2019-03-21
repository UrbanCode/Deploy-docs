# Connecting to clouds through HCL UrbanCode Deploy

The HCL® UrbanCode™ Deploy server can use virtual system patterns from cloud systems such as IBM® Cloud Orchestrator to create dynamic environments.

**Note:** If you installed a FIPS-compliant server as described in [Installing the server in interactive mode](../../com.udeploy.install.doc/topics/server_install_interactive.md), the HCL UrbanCode Deploy server cannot integrate with cloud systems through virtual system patterns. Your JVM connects to only FIPS 140-2 certified IBM providers. The blueprint design server can still connect to clouds through OpenStack Heat.

1.  Configure the cloud system to install agents automatically. See [Configuring virtual system pattern-based clouds](../../com.udeploy.install.doc/topics/cloud_configure.md).
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


**Parent topic:** [Overview of integrations](../topics/integrat_ov.md)

