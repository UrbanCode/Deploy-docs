# Installing the blueprint designer

The installation can include the blueprint design server and its engine and database.

Typically, the database, engine, and blueprint design server are installed on separate systems, although for a simple evaluation they can all be installed on the same system.

Install and configure the blueprint design server. To use the blueprint designer, you must complete the following steps:

1.  Acquire a Heat orchestration engine. To connect to OpenStack and OpenStack-based clouds, extend the existing Heat engine for the cloud; see [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md). To connect to non-OpenStack clouds, such as Amazon Web Services and MIcrosoft Azure, install an engine with HCL® UrbanCode™ Deploy; see [Installing the engine](install_engine.md).
2.  Configure a database for the blueprint design server. See [Blueprint design server database configuration](install_database_bds_ov.md).
3.  Install the blueprint design server. See [Installing the blueprint design server](install_server_bds.md).
4.  Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](ucdp_integrate.md).
5.  Integrate with the cloud. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
6.  Set up access control. See [Configuring security for the blueprint design server](../../com.udeploy.admin.doc/topics/security_ov.md).

-   **[Installing the engine](../../com.edt.doc/topics/install_engine.md)**  
To connect the blueprint design server to a cloud system, you need a Heat orchestration engine. Heat orchestration engines interpret blueprints and use them as patterns for cloud resources. To connect to OpenStack-based clouds, you extend the engine that is associated with the cloud. To connect to all other clouds, you install an engine with HCL UrbanCode Deploy.
-   **[Installing the blueprint design server](../../com.edt.doc/topics/install_server_bds.md)**  
Installing the blueprint design server involves installing an application on Apache Tomcat. You can install the blueprint design server in interactive mode or in silent mode.
-   **[Starting the HCL UrbanCode Deploy blueprint designer](../../com.edt.doc/topics/runProduct.md)**  
Both UNIX™ and Windows™ installations require the HCL UrbanCode Deploy server and at least one agent. If you are using a database other than Derby, make sure that the appropriate driver is installed and configured.
-   **[Backing up and recovering](../../com.edt.doc/topics/backup_recover.md)**  
You can back up and recover the contents of your HCL UrbanCode Deploy installation.
-   **[Installing test fixes to the engine](../../com.edt.doc/topics/engine_install_testfix.md)**  
Test fixes are provided by IBM® support to correct specific issues with the Heat orchestration engine. You replace individual files in the directory that contains the installed engine.

**Parent topic:** [Installing HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/install_ch.md)

