# Adding cold standby servers

You can add cold standby servers to serve as a backup server or for disaster recovery. You must start the secondary server or servers when the active server fails, and network traffic is routed to the secondary servers.

-   Make sure that the server is connected to a license server with available licenses.
-   Set up a cluster as described in [Setting up clusters of servers](../../com.ibm.udeploy.doc/topics/ha_config_server.md). Your cluster must contain at least one running server.

To set up a cold standby system, you install two or more servers on separate systems and connect the servers to the same database and network storage. Then, you configure a method to distribute the traffic to secondary servers if the primary servers fail. In most cases, you must manually start the secondary servers after the primary servers fail.

During failover, the secondary server reestablishes connections with all agents, runs recovery, and proceeds with any queued processes. HCL® UrbanCode™ Deploy has no automatic process for failover, but it can be managed by using your load balancer or DNS.

You can use cold standby servers with or without a load balancer. If you use a load balancer, instead of accessing the servers directly, users access the load balancer URL. To the users, that URL appears to host a single instance of the server with high capacity; the users are not aware of the multiple servers.

1.   Install the cold standby server: Install the server as described in [Installing the server in interactive mode](../../com.ibm.udeploy.install.doc/topics/server_install_interactive.md) with the following details:

    -   When the installation program asks for database information, specify the database that the cluster servers are using.
    -   If you are using a load balancer, when the installation program asks for the host name that users will access, specify the host name of the load balancer.
    -   When the installation program asks if the server is part of a high-availability cluster, say yes.
    -   When the installation program asks for the location of the application data, specify the same folder on the network storage that the other cluster servers are using.
    **Note:** Do not start the server.

2.   Set the new server to use the same security certificate as the existing servers. For example, you can copy the certificate in the /opt/tomcat/conf/tomcat.keystore file to the other servers. When you import the certificate into other servers, in the server.xml file, set the keyAlias property to point to the imported certificate.
3.   Set a method to route traffic to the cold standby server after failover. Depending on your network configuration, you might configure a DNS server routing path, Virtual IP, cluster connection, or load balancer to swap traffic. For information on cluster connections, see [Creating cluster connections](../../com.ibm.udeploy.admin.doc/topics/settings_network.md#).

