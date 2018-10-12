# Configuring the MobileFirst Platform Foundation Server {#configuringtheworklightserver .task}

You must configure the IBM® MobileFirst Platform Foundation Server before you can run the process steps to deploy mobile application artifacts.

For each MobileFirst Platform Foundation project, you must configure the MobileFirst Platform Foundation Server. The one time MobileFirst Platform Foundation Server setup and configuration options for the MobileFirst Platform Foundation project WAR file are described in the MobileFirst Platform Foundation product help. See [Deploying a project WAR file and configuring the application server](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/deploy/c_deploy_custom_war_file_to_app_server.html)

You can use any of the following methods to configure the MobileFirst Platform Foundation Server:

-   Use Ant tasks to configure the server:
    -   Use the command line to run the Ant script.
    -   Use the Ant process step within IBM UrbanCode® Deploy to run the Ant script with the MobileFirst Platform Foundation Ant tasks. To use the Ant process step, you must download and install the Ant plug-in for IBM UrbanCode Deploy.
-   Use the Server Configuration Tool to configure the server.
-   Manually configure the server.

**Tips:** 

-   Sample scripts are available for configuring the MobileFirst Platform Foundation server and are in MobileFirst\_installation\_directory/Worklight/WorklightServer/configuration-samples. The sample script combines the two steps in the following procedure by creating a database and deploying the project WAR file.
-   For information about configuring a secure MobileFirst Platform Foundation Console for IBM WebSphere® Application Server Liberty Profile and required values, see [Testing the Worklight® Console login screen](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.0.0/com.ibm.worklight.help.doc/admin/r_protecting_ibm_worklight_console.html).

1.  To configure the MobileFirst Platform Foundation Server for a MobileFirst Platform Foundation project:
2.  [Creating and configuring the databases](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/deploy/c_config_dbs.html): 

    |Option|Documentation|
    |------|-------------|
    |**Use Ant tasks to create and configure the databases**|[Creating and configuring the databases with Ant tasks](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/devref/r_ant_tasks_configure_dbs.html)|
    |**Use the Server Configuration Tool to create and configure the databases**|[Deploying, updating, and undeploying a Worklight Server by using the Server Configuration Tool](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/deploy/c_using_server_config_tool.html)|
    |**Manually create and configure the databases**|[Creating and configuring the databases manually](http://www-01.ibm.com/support/knowledgecenter/?lang=en#!/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/admin/c_manually_configuring_databases.html)|

3.  [Deploying a project WAR file and configuring the application server](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/deploy/c_deploy_custom_war_file_to_app_server.html): 

    |Option|Documentation|
    |------|-------------|
    |**Use Ant tasks to install the MobileFirst Platform Foundation project**|[Deploying a project WAR file and configuring the application server with Ant tasks](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/devref/r_ant_tasks_configure_appserver.html)|
    |**Use the Server Configuration Tool to install the MobileFirst Platform Foundation project**|[Deploying, updating, and undeploying a Worklight Server by using the Server Configuration Tool](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/deploy/c_using_server_config_tool.html)|
    |**Manually install the MobileFirst Platform Foundation project**|[Deploying a project WAR file and configuring the application server manually](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/admin/c_manually_configuring_app_server.html)|

    **Important:** If you are configuring multiple projects on a single MobileFirst Platform Foundation server, then see the MobileFirst Platform Foundation topic [Configuring multiple IBM Worklight projects](http://www-01.ibm.com/support/knowledgecenter/SSZH4A_6.1.0/com.ibm.worklight.deploy.doc/devref/c_ant_tasks_configuring_multiple_wl_projects.html). If you run multiple projects on a single MobileFirst Platform Foundation server, install the .war files from multiple MobileFirst Platform Foundation projects in the same application server, and then have them operate in parallel and independently.

    **Note:** The MobileFirst Platform Foundation project WAR file deployment that is described in this step is a one time configuration. When you deploy your mobile application, update the WAR file on the application server by using the plug-in process steps.


**Parent topic:** [Building and deploying mobile applications](../topics/plugins_worklight_buildanddeploy.md)

