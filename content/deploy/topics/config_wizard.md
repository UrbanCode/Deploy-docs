# Setting up the wizard for new users {#config_wizard .task}

IBM® UrbanCode® Deploy includes a wizard to help users become familiar with the procedures and steps in creating a deployment. Some configuration is required before the wizard can be used.

At least one agent must be installed and accessible to users to start and complete the introductory wizard.

The wizard is enabled with new installations of IBM UrbanCode Deploy. If you are working with an upgrade, the **Welcome** tab that includes the push button to open the wizard must be enabled. To enable the **Welcome** tab, open the installed.properties file, and add this entry: `server.enable.welcome.tab=true`. By default, this file is in this folder: `/opt/ibm-ucd/server/conf/server`.

1.  **Tip:** You don't have to create a role to assign so that they can follow the wizard. You can assign users to the Automation Engineer role, which is included on the server during installation. This Automation Engineer role has all the permissions that are required to complete the introductory wizard. If you want to create a separate role for wizard users, complete this procedure.

2.   Create a role with these permissions: 
    -   Create Application
    -   Create Component
    -   Create Environment
    -   Create Resource
    -   View Agent
3.   Give this role access to at least one agent. 
4.   Assign this role to users so that they can start and follow the wizard. 

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

