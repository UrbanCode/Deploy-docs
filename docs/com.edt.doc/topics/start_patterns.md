# Starting the blueprint designer, cloud discovery service, and engine

To start the blueprint designer and its associated services, you must start the cloud discovery service, the blueprint design server, and the engine Heat services.

Depending on your system configuration, these components might be on different computers. Be sure to start the cloud discovery service, the blueprint design server, and the engine Heat services on the correct computers.

**Parent topic:** [Starting the HCL UrbanCode Deploy blueprint designer](../../com.edt.doc/topics/runProduct.md)

## Starting the cloud discovery service

1.   Start the cloud discovery service: 

    -   On Linux™ systems that manage services with the systemd system manager, use the systemctl command:

        ```
        systemctl start ibm-cloud-discovery.service
        ```

        **Note:** If you start the cloud discovery service with the systemctl command, you must use the systemctl command to stop the cloud discovery service.

    -   On Linux systems that do not use the systemd system, run the following command:

        ```
        cloud-discovery-service &
        ```

    On Windows™, run the following command:

    ```
    C:\python\_installation\_directory\Scripts\cloud-discovery-service.exe
    ```

    Use the location where Python is installed for `python\_installation\_directory`. The default installation directory is C:\\Python27. By default, the command looks like this code:

    ```
    C:\Python27\Scripts\cloud-discovery-service.exe
    ```


## Starting the engine Heat services

1.   Restart the engine database. Run the following command:

    ```
    systemctl start mariadb.service
    ```

2.   Restart the RabbitMQ service. Run the following command:

    ```
    systemctl start rabbitmq-server.service
    ```

3.   Start the Heat services. Run the following commands:

    ```
    systemctl start openstack-heat-engine.service
    ```

    ```
    systemctl start openstack-heat-api.service
    ```

    ```
    systemctl start openstack-heat-api-cfn.service
    ```

    ```
    systemctl start openstack-heat-api-cloudwatch.service
    ```

4.   If you use the default Keystone service that is provided with the engine, start it. Run the following command:

    ```
    systemctl start openstack-keystone.service
    ```


## Starting the blueprint design server

1.   Start the blueprint design server: 
    -   On Linux, run the following command:

        ```
        server\_installation\_directory/bin/server start
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        /opt/ibm-ucd-patterns/bin/server start
        ```

    -   On Windows, run the following command:

        ```
        C:\server\_installation\_directory\bin\start_server
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is C:\\Program Files\\ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        "C:\Program Files\ibm-ucd-patterns\bin\start_server"
        ```


