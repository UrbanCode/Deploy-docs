# Setting up high-availability clusters {#server_install_clustered .task}

To configure a high-availability cluster, you store shared files on network storage. Then, you configure multiple servers, set each server to access the same files and database, and configure a load balancer to distribute the traffic between the servers.

The specific steps depend on whether you are clustering servers, blueprint design servers, or engines.

-   To set up a cluster of servers, see [Setting up clusters of servers](ha_config_server.md).
-   To set up a cluster of blueprint design servers, see [Setting up clusters of blueprint design servers](ha_config_bds.md).
-   To set up a cluster of engines, see [Setting up clusters of engines](ha_config_engine.md).

To upgrade a high-availability installation, see [Upgrading high-availability installations](../../com.ibm.udeploy.admin.doc/topics/ha_upgrading.md).

-   **[Setting up clusters of servers](../topics/ha_config_server.md)**  
To configure a cluster of servers, set up a shared database and file system for the servers to use.
-   **[Adding servers to clusters](../topics/ha_add_server.md)**  
You can add new servers to a cluster at installation time, or you can move existing servers to be part of a cluster.
-   **[Converting a stand-alone server to high availability](../topics/ha_convert_server.md)**  
You can convert an IBM® UrbanCode® Deploy server into the first node of a high-availability cluster.
-   **[Setting up clusters of blueprint design servers](../../com.ibm.edt.doc/topics/ha_config_bds.md)**  
You can set up clusters of blueprint design servers for a high-availability configuration. As with setting up clusters of servers, you store shared files on a system and set multiple blueprint design servers to use those files.
-   **[Adding blueprint design servers to clusters](../../com.ibm.edt.doc/topics/ha_add_bds.md)**  
To add a blueprint design server to a cluster, connect it to the shared database and network storage. Then, configure the load balancer to send traffic to it.
-   **[Setting up clusters of engines](../../com.ibm.edt.doc/topics/ha_config_engine.md)**  
To set up clusters of engines, you store shared files on a system and set multiple engines to use those files.
-   **[Adding engines to clusters](../../com.ibm.edt.doc/topics/ha_add_engine.md)**  
To add an engine to a cluster, connect it to the shared database. Then, configure the load balancer to send traffic to it.
-   **[Creating cluster connections](../../com.ibm.udeploy.admin.doc/topics/settings_network.md)**  
A server connection to a cluster \(formerly known as a network relay\) is a setting on an IBM® UrbanCode® Deploy server that opens a Java™ Message Service \(JMS\) port for communication with other servers. These cluster connections are necessary for servers in a cluster to communicate.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

