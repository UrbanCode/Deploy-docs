# Upgrading the server

You can upgrade the HCL® UrbanCode™ Deploy server to incorporate to a later version. Always upgrade agents, agent relays, and the blueprint design server in addition to upgrading the server. Upgrading the server, agents, agent relays, and blueprint design server are each completed independently. Unless specified, upgrade the server before you upgrade the agents.

Upgrading the HCL UrbanCode Deploy server can be performed using the same methods as an initial installation. However, there are a number of considerations that must be taken into account during an upgrade. Read the following sections before performing the upgrade. The upgrade process is a complete replacement of the server.

**Note:** When you upgrade the server, installed plug-ins are upgraded to newer versions. The updated plug-ins are not necessarily compatible with an earlier version. When you upgrade, previous versions of the plug-ins are kept on the server. You cannot create processes with previous versions of plug-ins, but you can deploy snapshots that use the old versions of the plug-ins.

-   **[Upgrading the server in interactive mode](../../com.udeploy.install.doc/topics/upgrade_server.md)**  
To upgrade the server, stop the server and run the new installation program.
-   **[Upgrading the server in silent mode](../../com.udeploy.install.doc/topics/upgrade_server_silent.md)**  
Use silent mode to upgrade without command-line prompts. To upgrade the server, stop the server, edit the properties file, and run the new installation program. These instructions apply to upgrades to versions 6.0 and later.

**Parent topic:** [Upgrading and migrating](../../com.udeploy.doc/topics/c_node_upgrading.md)

