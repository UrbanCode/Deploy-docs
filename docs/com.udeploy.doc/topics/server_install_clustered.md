# Setting up high-availability clusters

To configure a high-availability cluster, you store shared files on network storage. Then, you configure multiple servers, set each server to access the same files and database, and configure a load balancer to distribute the traffic between the servers.

The specific steps depend on whether you are clustering servers, blueprint design servers, or engines.

-   To set up a cluster of servers, see [Setting up clusters of servers](ha_config_server.md).
-   To set up a cluster of blueprint design servers, see [Setting up clusters of blueprint design servers](ha_config_bds.md).
-   To set up a cluster of engines, see [Setting up clusters of engines](ha_config_engine.md).

To upgrade a high-availability installation, see [Upgrading high-availability installations](../../com.udeploy.admin.doc/topics/ha_upgrading.md).

-   **[Setting up clusters of servers](../topics/ha_config_server.md)**  
To configure a cluster of servers, set up a shared database and file system for the servers to use.
-   **[Adding servers to clusters](../topics/ha_add_server.md)**  
You can add new servers to a cluster at installation time, or you can move existing servers to be part of a cluster.
-   **[Converting a stand-alone server to high availability](../topics/ha_convert_server.md)**  
You can convert an HCL® UrbanCode™ Deploy server into the first node of a high-availability cluster.
-   **[Creating cluster connections](../../com.udeploy.admin.doc/topics/settings_network.md)**  
A server connection to a cluster \(formerly known as a network relay\) is a setting on an HCL® UrbanCode™ Deploy server that opens a Java™ Message Service \(JMS\) port for communication with other servers. These cluster connections are necessary for servers in a cluster to communicate.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

