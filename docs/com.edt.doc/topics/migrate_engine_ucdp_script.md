# Migrating engines that you installed with HCL UrbanCode Deploy

To migrate the Heat engine that is required for the HCL® UrbanCode™ Deploy blueprint designer from Red Hat Enterprise Linux™ \(RHEL\) version 6 to RHEL 7, stop the related Heat services, migrate the databases, install the new version, and restart the services

-   You must have installed a Heat engine that was provided with HCL UrbanCode Deploy version 6.2.1.0 or earlier.
-   You must have `root` access to the RHEL 6 system that hosts the Heat engine.
-   You must use the default user name and password for the Heat engine's MySQL database. If the database user name is not root or the root user's MySQL password is not passw0rd, you must update the values for the DBUSER and DBPASSWD parameters in the /extracted\_location/ibm-ucd-patterns-install/engine\_install/resources/tools/fromJuno2Kilo-prep.sh file, where extracted\_location is where you extracted the engine installation media.
-   You must have access to the Heat engine and Keystone service by using the command line interface.
-   You must have access to a server that runs RHEL 7 and can host the new engine. Configure the target system with the prerequisites that are listed in [Installing an engine in interactive mode](install_engine_interactive.md).
-   If you connect to an OpenStack cloud, then you must upgrade the cloud to the Kilo version.

In HCL UrbanCode Deploy version 6.2.1.1, the default Heat engine was changed from a Juno version that must be installed on RHEL 6 to a Kilo engine that must be installed on RHEL 7. To upgrade the engine, you must migrate your engine to a new server. If you installed the default OpenStack Identity Service \(Keystone\), you must also migrate it.

These steps are for engines that you installed with the HCL UrbanCode Deploy installer. If you extended an existing engine as described in [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md), use the instructions in [Upgrading engines that you extended](upgrade_engine_extended.md). These steps include instructions to also migrate a default OpenStack Identity Service \(Keystone\) to the new server.

If you do not want to migrate the engine, but you need access to the updated Heat types, extend your existing engine. See [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md#).

To upgrade an engine to a version before 6.2.1.1 to version 6.2.1.1 or later, see [Installing an engine in interactive mode](install_engine_interactive.md#).

1.   On the system that hosts the OpenStack Juno engine, remove all of the environments that have the status of `CREATE_FAILED`: 
    1.   Run the following command to identify the environments: 

        ```
        heat stack-list | grep CREATE_FAILED
        ```

    2.   Delete each environment by running the following command: 

        ```
        heat stack-delete stackID
        ```

        Use the ID of the environment for `stackID`.

2.   To reduce the size of the database for the Keystone service, remove expired security tokens. Run the following command to remove the expired tokens:

    ```
    keystone-manage token_flush
    ```

3.   Stop the Heat services by running the following commands: 

    ```
    service openstack-heat-engine stop
    ```

    ```
    service openstack-heat-api stop
    ```

    ```
    service openstack-heat-api-cfn stop
    ```

    ```
    service openstack-heat-api-cloudwatch stop
    ```

4.   Stop the Keystone service by running the following command: 

    ```
    service openstack-keystone stop
    ```

5.   Copy the fromJuno2Kilo-prep.sh file from the installation media of HCL UrbanCode Deploy version 6.2.1.1 or later to the system that hosts the OpenStack Juno engine. The file is in the /extracted\_location/ibm-ucd-patterns-install/engine\_install/resources/tools folder, where extracted\_location is the location to which you extracted the installation media.
6.   To package the database backups and configuration files that the new system requires, on the system that hosts the OpenStack Juno engine, run the following command: 

    ```
    /transfer\_location/fromJuno2Kilo-prep.sh
    ```

    where transfer\_location is the folder that you transferred the file to. Backup files for the Heat engine and Keystone service and necessary configuration files are stored in the ./migration.toolkit.number.tar.gz file, where number represents the time of package creation.

7.   Transfer the ./migration.toolkit.number.tar.gz to the RHEL 7 computer and extract it. The extracted files are in the /transfer\_location/migration.toolkit.number folder, where number represents the time of package creation.
8.   On the RHEL 7 computer, install a new engine and Keystone service and start their services. See [Installing the engine](install_engine.md#).
9.   Verify that the engine installed correctly. 
    1.   Change directory to the /root/ folder. 
    2.   To verify that the engine is running, run the following commands: 

        ```
        source clientrc
        ```

        ```
        heat resource-type-list
        ```

        ```
        heat stack-list
        ```

        If the Heat engine is running, the resource types and stacks that the engine contains are displayed.

10.  Review the contents of the heat.conf, keystone.conf, and my.cnf files that are in the /transfer\_location/engine.info.number/conf, and add any custom values that they contain to the following files: 
    -   /etc/heat/heat.conf
    -   /etc/keystone/keystone.conf
    -   /etc/my.cnf
11.  Migrate the databases for the Heat engine and Keystone service by running the following command: 

    ```
    /extracted\_location/migration.toolkit.number/fromJuno2Kilo.sh host\_name
    ```

    where extracted\_location is the location to which you extracted the /migration.toolkit.number.tar.gz folder and host\_name is the fully qualified host name or IP address of the RHEL 7 system.

12.  Configure the new Heat engine and Keystone service. After you migrate the databases for the Heat engine and Keystone service, you must create the OpenStack project, users, and roles that are used in the databases. You must also configure new OpenStack identity endpoints for the new Keystone service. To complete these setup and configuration scripts, run the add-keystonev3-after-migration.sh script that is provided with the engine installation media.

    Run the following command:

    ```
    /extracted\_location/ibm-ucd-patterns-install/engine_install/resources/tools/add-keystonev3-after-migration.sh
    ```

    In this command, extracted\_location is the location to which you extracted the installation media.

13.  Stop and start the engine. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md#) and [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md#).
14.  In the system settings in the blueprint designer, update the new URLs for the Keystone service and Heat engine, and then test the connections. 
15.  On the **Environments** page, confirm that your environments are listed. 
16.  To confirm that the Heat engine functions correctly, create a blueprint and provision it. See [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md#).

**Parent topic:** [Upgrading engines](../../com.edt.doc/topics/upgrade_engine.md)

