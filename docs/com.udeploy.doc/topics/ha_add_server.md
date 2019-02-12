# Adding servers to clusters

You can add new servers to a cluster at installation time, or you can move existing servers to be part of a cluster.

**Parent topic:** [Setting up high-availability clusters](../topics/server_install_clustered.md)

## Installing new cluster servers

The easiest way to add servers to a cluster is to install new servers. The installation program sets them up to be part of the cluster.

-   Set up a cluster of servers, including setting up a load balancer, shared database, and network storage. See [Setting up clusters of servers](ha_config_server.md).
-   Each server must run the same version of HCL® UrbanCode™ Deploy.
-   Ensure that each server can connect to each other server on the network. For example, ensure that your firewall rules allow the servers to communicate over HTTPS and JMS.

1.   On the system on which you are installing the new server, set up a connection to the network storage. For example, on Linux™ systems, you might mount a remote drive to the local file system.
2.   Install the server as described in [Installing the server in interactive mode](../../com.udeploy.install.doc/topics/server_install_interactive.md) with the following details: 
    -   When the installation program asks for database information, specify the shared database for the cluster.
    -   When the installation program asks for the host name for users to access, specify the host name of the load balancer.
    -   When the installation program asks whether the server is part of a high-availability cluster, specify yes.
    -   When the installation program asks for the location of the application data, specify the same folder on the network storage that the other cluster servers are using. If this is the first server in the cluster, you can specify any folder on the network storage. In this case, other servers that you add to the cluster must also use this folder.
3.   Set the new server to use the same security certificate as the existing servers. For example, you can copy the certificate in the /opt/tomcat/conf/tomcat.keystore file to the other servers. When you import the certificate into other servers, in the server.xml file, set the keyAlias property to point to the imported certificate.
4.   If there are other servers in the cluster, create a cluster connect on one of the existing servers to the new server. See [Creating cluster connections](../../com.udeploy.admin.doc/topics/settings_network.md).
5.   Configure the load balancer to send HTTP/HTTS traffic to the new cluster server. 

## Moving existing servers to a cluster

-   Set up a cluster of servers, including setting up a load balancer, shared database, and network storage. See [Setting up clusters of servers](ha_config_server.md).
-   Each server must run the same version of HCL UrbanCode Deploy.
-   Ensure that each server can connect to each other server on the network. For example, ensure that your firewall rules allow the servers to communicate over HTTPS and JMS.

1.   On the system that hosts the server, set up a connection to the network storage. For example, on Linux systems, you might mount a remote drive to the local file system.
2.   If the sever contains elements that you want to keep, such as components, applications, or processes, export those elements and import them into an existing cluster server. 
3.   Stop the server. 
4.   Edit the installed.properties file on the server, located in the install\_folder/conf/server directory. 
    1.   Set the server.appdata.dir property to the location of the application data folder that the cluster servers are using. 
    2.   Copy the value of the encryption.keystore.alias property to the equivalent file on the new cluster server from a server that is already in the cluster. 
    3.   Add the following line of code to the file: 

        ```
        com.urbancode.ds.UDeployServer.multiserver=true
        ```

    4.   Update the database settings to use the same database as the other servers in the cluster. 
5.   Set the new server to use the same security certificate as the existing servers. For example, you can copy the certificate in the /opt/tomcat/conf/tomcat.keystore file to the other servers. When you import the certificate into other servers, in the server.xml file, set the keyAlias property to point to the imported certificate.
6.   Start the server. 
7.   On the new cluster server, click **Settings** \> **System Settings**, and set the **External Agent URL** and the **External User URL** to the URL for the load balancer. 
8.   Click **Save**. 
9.   On one of the existing cluster servers, create a network relay to the new server. See [Creating cluster connections](../../com.udeploy.admin.doc/topics/settings_network.md).
10.  If the server has any agents or agent relays, configure them for failover. See [Configuring agents for failover](../../com.udeploy.install.doc/topics/configure_agent_failover.md) and [Configuring agent relays for failover](../../com.udeploy.install.doc/topics/configure_relay_failover.md).

