# Upgrading and migrating

Learn how to upgrade HCL® UrbanCode™ Deploy elements, including the server, agents, and blueprint design server, and how to migrate data.

-   **[Upgrading the server](../../com.udeploy.install.doc/topics/upgradeInstall.md)**  
You can upgrade the HCL UrbanCode Deploy server to incorporate to a later version. Always upgrade agents, agent relays, and the blueprint design server in addition to upgrading the server. Upgrading the server, agents, agent relays, and blueprint design server are each completed independently. Unless specified, upgrade the server before you upgrade the agents.
-   **[Upgrading high-availability installations](../../com.udeploy.admin.doc/topics/ha_upgrading.md)**  
All servers that are configured for the HA feature must be on the same version. Thus, all servers must be upgraded at the same time.
-   **[Upgrading agents](../../com.udeploy.install.doc/topics/upgradeAgents.md)**  
In most cases, you upgrade agents from the server interface, but you can also upgrade the agents from the command line. Always upgrade agents and agent relays in addition to upgrading the server.
-   **[Upgrading agent relays](../../com.udeploy.install.doc/topics/upgrade_agent_relay.md)**  
When you upgrade the server, be sure to always upgrade agents and agent relays.
-   **[Upgrading encryption key strength](../../com.udeploy.install.doc/topics/upgrade_key_strength.md)**  
When you upgrade the server from version 6.0.1.1 or earlier to a version later than version 6.0.1.1, you can upgrade the SSL encryption.
-   **[Migrating the server database](../../com.udeploy.install.doc/topics/migrate_database.md)**  
The server installation files include a script that migrates the server database from Derby to another database system. You can not migrate from any database other than Derby.
-   **[Automatic upgrades of files stored in the server CodeStation](../../com.udeploy.install.doc/topics/t_upgrade_to_new_format.md)**  
When you upgrade to HCL UrbanCode Deploy version 6.1 or later, the server automatically upgrades all artifacts that are stored in its CodeStation.
-   **[Upgrading the blueprint design server](../../com.edt.doc/topics/upgrade_server_bds.md)**  
To upgrade the blueprint design server, stop the Tomcat server, install the new version, and restart the blueprint design server. When you upgrade the blueprint design server, you must also upgrade the engine.
-   **[Upgrading engines](../../com.edt.doc/topics/upgrade_engine.md)**  
The instructions that you use to upgrade an engine depends on how you installed the engine. When you upgrade the engine, you must also upgrade the blueprint design server.
-   **[Moving blueprints and configuration files](../../com.edt.doc/topics/migrate_ov.md)**  
After you upgrade from a version of the blueprint design server earlier than version 6.1.1, you must move blueprints and configuration files from the file system to the Git repository.

