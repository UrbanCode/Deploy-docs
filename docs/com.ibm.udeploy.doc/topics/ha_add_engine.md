# Adding engines to clusters

To add an engine to a cluster, connect it to the shared database. Then, configure the load balancer to send traffic to it.

-   These steps are appropriate for engines that you install with HCL® UrbanCode™ Deploy and use to connect to non-OpenStack clouds. To set up clusters of OpenStack engines that you use to connect to OpenStack clouds, see the OpenStack documentation.
-   Set up a cluster of engines, including setting up a load balancer and shared database. See [Setting up clusters of engines](ha_config_engine.md).
-   Each engine must run the same version of HCL UrbanCode Deploy.

You can add many engine nodes to the cluster as you need.

1.   On the new node, install the engine as described in [Installing the engine](../../com.ibm.udeploy.install.doc/topics/install_engine.md). For the public address of the system, specify the IP address of the load balancer. For the Keystone server, use the same Keystone server that you would use if you were installing a single engine.
2.   After you install the engine, stop the Heat services. 
    -   On Red Hat Enterprise Linux™ \(RHEL\) version 6, run the following commands:

        ```
        cd /etc/init.d
        ```

        ```
        for s in $(ls openstack*); do service $s stop; done
        ```

    -   For an engine that was provided with HCL UrbanCode Deploy version 6.2.1.1 or later on RHEL version 7, run the following command:

        ```
        /extracted\_location/ibm-ucd-patterns-install/engine-install/resources/tools/engine-tools.sh -r
        ```

        In this command, extracted\_location is the location of the installation files. This example is split onto separate lines for clarity, but the command must be entered on a single line.

3.   If you use an engine that is provided with HCL UrbanCode Deploy version 6.2.1.1 or later, configure the engine for the cluster by running a script. The script configures the Heat engine on this node to use the shared MariaDB database and RabbitMQ service that you installed for the cluster of Heat engine servers. The script is provided with the installation media for the Heat engine. You can run this script on only a Red Hat Enterprise Linux \(RHEL\) version 7 server. Run the script by using the following command:

    ```
    /extracted\_location/ibm-ucd-patterns-install/engine-install/resources/tools/ha/add-engine2cluster.sh
    -a allowed\_uris
    -d database\_url
    -k keystone\_host
    -r rabbitmq\_host
    ```

    In this command, extracted\_location is the location of the installation files, and you must provide a value for each option.

    |Option|Description|
    |------|-----------|
    |`-a`|Set the authorized Keystone URIs. Separate each URI with a comma. For example, `http://first\_keystone:5000/v3,http://second\_keystone:5000/v2.0` |
    |`-d`|Set the URL of the Heat engine MariaDB database. For example, `jdbc:mariadb://heat:heat@engine-database.example.com:3306/heat?charset=utf8`|
    |`-k`|Set the Keystone host. For example, `engine-database.example.com`|
    |`-r`|Set the RabbitMQ host. For example, `engine-database.example.com`|

4.   If you use an engine that is provided with versions of HCL UrbanCode Deploy before 6.2.1.1, configure the engine for the cluster by completing the following steps. The steps configure the Heat engine on this node to use the shared MySQL database and RabbitMQ service that you installed for the cluster of Heat engine servers. These commands are for RHEL version 6 servers.
    1.   Stop the MySQL database and prevent it from starting at system startup by running the following commands: 

        ```
        service mysqld stop
        ```

        ```
        chkconfig mysqld off
        ```

        The engine does not require this service because it must use the shared engine database. If the cluster node does not require MySQL for any other purpose, you can uninstall MySQL from the cluster node.

    2.   Open the /etc/heat/heat.conf file in a text editor. 
    3.   In the /etc/heat/heat.conf file, if you are connecting to a Keystone engine other than the default Keystone engine for the cloud, find the allowed\_auth\_uris property, and add the complete URL to the Keystone server to the property value. For example, if the engine connects to clouds at `cloud1.example.com` and `cloud2.example.com`, the property might look like the following example:

        ```
        allowed_auth_uris=http://cloud1.example.com:5000/v2.0,http://cloud2.example.com:5002/v2
        ```

    4.   Find the sql\_connection property, and change it to the location of the shared engine database. For example, if the shared engine database has the host name `engine-database.example.com`, the property looks as follows:

        ```
        sql_connection=mysql://heat:heat@engine-database.example.com:3306/heat?charset=utf8
        ```

    5.   Find the auth\_host property, and update it to point to the load balancer host name, as in the following example: 

        ```
        auth_host=ucd-patterns.example.com
        ```

    6.   Find the rabbit\_host property, and update it to point to the host name of the shared engine database, as in the following example: 

        ```
        rabbit_host=engine-database.example.com
        ```

    7.   Stop the RabbitMQ service: 

        ```
        service rabbitmq-server stop
        ```

    8.   Prevent the RabbitMQ service from starting on system startup: 

        ```
        chkconfig rabbitmq-server off
        ```

    9.   Open the /etc/keystone/keystone.conf file in a text editor. 
    10.  In the /etc/keystone/keystone.conf file, find the connection parameter and update it to use shared engine database, as in the following example: 

        ```
        connection=mysql://keystone:keystone@engine-database.example.com:3306/keystone?charset=utf8
        ```

    11.  Start the Heat services by running the following commands: 

        ```
        cd /etc/init.d
        ```

        ```
        for s in $(ls openstack*); do service $s start; done
        ```

        ```
        for s in $(ls openstack*); do service $s status; done
        ```

5.   If you configured the engine by using a script, for only the first engine in the cluster, complete the following steps: 
    1.   Synchronize the Keystone server and Heat engine databases. Run the following commands:

        ```
        keystone-manage db_sync
        heat-manage db_sync
        ```

    2.   To initialize the OpenStack endpoints for the engine cluster, run the `configure-os-services.sh` script. Run the script by using the following command:

        ```
        /extracted\_location/ibm-ucd-patterns-install/engine-install/resources/tools/ha/configure-os-services.sh
        ```

6.   Configure the load balancer to send traffic on the following ports to the new engine node: 

    -   5000
    -   35357
    -   8004
    -   8000
    -   8003
    For example, if you are using HAProxy, the configuration file might have code that is similar to the following snippets. In this code example, it is assumed that the engine nodes have these host names: `engine1.example.com`, `engine2.example.com`, and `engine3.example.com`.

    ```
    frontend keystone_api
        bind *:5000
        default_backend keystone_api_back
    
    frontend keystone_admin
        bind *:35357
        default_backend keystone_admin_back
    
    frontend heat_api
        bind *:8004
        default_backend heat_api_back
    
    frontend heat_cfn
        bind *:8000
        default_backend heat_cfn_back
    
    frontend heat_cloudwatch
        bind *:8003
        default_backend heat_cloudwatch_back
    ```

    ```
    
    backend keystone_api_back
        balance     roundrobin
        server      enginenode1 engine1.example.com:5000 check
        server      enginenode2 engine2.example.com:5000 check
        server      enginenode3 engine3.example.com:5000 check
        option      httpchk
    
    backend keystone_admin_back
        balance     roundrobin
        server      enginenode1 engine1.example.com:35357 check
        server      enginenode2 engine2.example.com:35357 check
        server      enginenode3 engine3.example.com:35357 check
        option      httpchk
    
    backend heat_api_back
        balance     roundrobin
        server      enginenode1 engine1.example.com:8004 check
        server      enginenode2 engine2.example.com:8004 check
        server      enginenode3 engine3.example.com:8004 check
        option      httpchk
    
    backend heat_cfn_back
        balance     roundrobin
        server      enginenode1 engine1.example.com:8000 check
        server      enginenode2 engine2.example.com:8000 check
        server      enginenode3 engine3.example.com:8000 check
        option      httpchk
    
    backend heat_cloudwatch_back
        balance     roundrobin
        server      enginenode1 engine1.example.com:8003 check
        server      enginenode2 engine2.example.com:8003 check
        server      enginenode3 engine3.example.com:8003 check
        option      httpchk
    ```

7.   Restart the HAProxy service: 

    ```
    service haproxy restart
    ```

8.   On the new engine node, run the following commands to verify that the engine is running: 

    ```
    source ˜/clientrc
    ```

    ```
    heat stack-list
    ```

    ```
    keystone endpoint-list
    ```

    The endpoints that the keystone endpoint-list command returns must refer to the load balancer and not the engine node.

9.   Verify that the load balancer is sending traffic to the new node. For example, if HAProxy is installed on a system with the host name `ucd-patterns.example.com`, you can go to the following URL to see the status of the nodes: `http://ucd-patterns.example.com:1936/haproxy?stats` 

The engine is part of the cluster.

