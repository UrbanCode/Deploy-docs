# Upgrading engines that you installed with HCL UrbanCode Deploy

To upgrade the engine, stop the related Heat services, install the new version, and restart the services. When you upgrade the engine, you must also upgrade the blueprint design server.

These steps are for engines that you installed with the HCL® UrbanCode™ Deploy installer in versions before 6.2.1.1. For all other engines, other processes apply:

-   To upgrade an engine from before 6.2.1.1 to version 6.2.1.1 or later, you must transfer the engine from a Red Hat Enterprise Linux™ version 6 server to a Red Hat Enterprise Linux version 7 server. See [Migrating engines that you installed with HCL UrbanCode Deploy](migrate_engine_ucdp_script.md#). If you do not want to migrate the engine, but you need access to the updated Heat types, extend your existing engine. See [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md#).
-   If you are upgrading an engine that is version 6.2.1.1 or later, use the instructions in [Upgrading engines that you extended](upgrade_engine_extended.md).
-   If you extended an existing engine as described in [Extending an existing OpenStack engine](extending_an_engine_for_openstack.md), use the instructions in [Upgrading engines that you extended](upgrade_engine_extended.md).

1.   Stop the cloud discovery service. See [Stopping the blueprint designer, cloud discovery service, and engine](stop_patterns.md).
2.   Check to see whether the program `rabbitmq-server` is running: 

    ```
    service rabbitmq-server status
    ```

3.   If the program `rabbitmq-server` is running, stop it: 

    ```
    service rabbitmq-server stop
    ```

4.   Check to see whether the program `qpidd` is running: 

    ```
    service qpidd status
    ```

5.   If the program `qpidd` is running, stop it: 

    ```
    service qpidd stop
    ```

6.   Stop the Heat services by running the following commands: 

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

7.   If you installed a Keystone server along with the engine, stop it: 

    ```
    service openstack-keystone stop
    ```

8.   Install the new version of the engine. See [Installing the engine](install_engine.md).
9.   Start the Heat services: 

    ```
    service openstack-heat-engine start
    ```

    ```
    service openstack-heat-api start
    ```

    ```
    service openstack-heat-api-cfn start
    ```

    ```
    service openstack-heat-api-cloudwatch stop
    ```

10.  If you installed a Keystone server when you installed the engine, start it by running the following command: 

    ```
    service openstack-keystone start
    ```

11.  Start the cloud discovery service. See [Starting the blueprint designer, cloud discovery service, and engine](start_patterns.md).

A new file is in the /etc/heat/ folder. It is named /etc/heat/heat.conf.backup.n, where n is the largest numerical value for the present `.backup` files. You can still find the previous heat.conf files in this location.

If you installed a Keystone server with your engine, new files are in the /etc/keystone/ and /root/ folders. They are named /etc/keystone/keystone.conf.backup.n and /root/keystonerc.backup.n files, where n is the largest numerical value for the present `.backup` files. These files contain the new service token value for your Keystone server. You can still find the previous keystone.conf and keystonerc files in those locations. Similarly, the file ~/clientrc file is backed up.

**Parent topic:** [Upgrading engines](../../com.ibm.edt.doc/topics/upgrade_engine.md)

