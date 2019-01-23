# Upgrading engines

The instructions that you use to upgrade an engine depends on how you installed the engine. When you upgrade the engine, you must also upgrade the blueprint design server.

-   To upgrade an engine that you installed with the HCL® UrbanCode™ Deploy installer in versions before 6.2.1.1, see [Upgrading engines that you installed with HCL UrbanCode Deploy](upgrade_engine_ucdp.md).
-   To upgrade from a version before 6.2.1.1 to version 6.2.2 or later, you can either migrate or extend the engine. See [Migrating engines that you installed with HCL UrbanCode Deploy](migrate_engine_ucdp_script.md#) and [Upgrading engines that you extended](upgrade_engine_extended.md).
-   To upgrade an engine that you installed with the HCL UrbanCode Deploy installer in versions 6.2.1.1 and later, see [Upgrading engines that you extended](upgrade_engine_extended.md).
-   To upgrade engines that you extended as described in [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md), see [Upgrading engines that you extended](upgrade_engine_extended.md).

-   **[Upgrading engines that you installed with HCL UrbanCode Deploy](../../com.ibm.edt.doc/topics/upgrade_engine_ucdp.md)**  
To upgrade the engine, stop the related Heat services, install the new version, and restart the services. When you upgrade the engine, you must also upgrade the blueprint design server.
-   **[Migrating engines that you installed with HCL UrbanCode Deploy](../../com.ibm.edt.doc/topics/migrate_engine_ucdp_script.md)**  
To migrate the Heat engine that is required for the HCL UrbanCode Deploy blueprint designer from Red Hat Enterprise Linux \(RHEL\) version 6 to RHEL 7, stop the related Heat services, migrate the databases, install the new version, and restart the services
-   **[Upgrading engines that you extended](../../com.ibm.edt.doc/topics/upgrade_engine_extended.md)**  
To upgrade a Heat orchestration engine that you extended, rerun the script that extends the engine.

**Parent topic:** [Upgrading and migrating](../../com.ibm.udeploy.doc/topics/c_node_upgrading.md)

