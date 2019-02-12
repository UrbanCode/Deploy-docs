# Stopping the blueprint designer, cloud discovery service, and engine

To stop the blueprint designer and its associated services, you must stop the cloud discovery service, the blueprint design server, and the engine Heat services.

Depending on your system configuration, these components might be on different computers. Be sure to stop the cloud discovery service, the blueprint design server, and the engine Heat services on the correct computers.

## Stopping the cloud discovery service

1.   Stop the cloud discovery service. On version 6.1.1.1 and later, the cloud discovery service is installed along with the blueprint design server.
    -   On Linux™ systems that manage services with the systemd system manager, use the systemctl command:

        ```
        systemctl stop ibm-cloud-discovery.service
        ```

        **Note:** If you started the cloud discovery service with the systemctl command, you must use the systemctl command to stop the cloud discovery service.

    -   On other versions of Linux:
        -   Using the ps command, find the process IDs of the cloud discovery service:

            ```
            ps aux | grep -i -e "cloud" | grep -v "grep"
            ```

            For example, the output of the command might look like the following code:

            ```
            root      1218  0.0  1.5 319048 29932 ?        Sl   Dec08   0:00 /usr/bin/python /usr/bin/cloud-discovery-service
            
            ```

        -   Using the kill command, stop the processes. For example:

            ```
            kill 1218
            ```

    -   On Windows™:
        -   Using the Task Manager program, find the cloud-discovery-service process.
        -   Right-click the cloud-discovery-service process and click **End task**.

## Stopping the blueprint design server

1.   Stop the blueprint design server: 

    ```
    server\_installation\_directory/bin/server stop
    ```

    Use the server installation directory for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns on Linux and C:\\Program Files\\ibm-ucd-patterns on Windows. By default, the command looks like this code:

    ```
    /opt/ibm-ucd-patterns/bin/server stop
    ```


## Stopping the engine Heat services

1.   Stop the Heat services. Run the following commands:

    ```
    systemctl stop openstack-heat-engine.service
    ```

    ```
    systemctl stop openstack-heat-api.service
    ```

    ```
    systemctl stop openstack-heat-api-cfn.service
    ```

    ```
    systemctl stop openstack-heat-api-cloudwatch.service
    ```

2.   If you installed a Keystone server when you installed the engine, stop it. Run the following command:

    ```
    systemctl stop openstack-keystone.service
    ```


