# Creating cluster connections

A server connection to a cluster \(formerly known as a network relay\) is a setting on an HCL® UrbanCode™ Deploy server that opens a Java™ Message Service \(JMS\) port for communication with other servers. These cluster connections are necessary for servers in a cluster to communicate.

Ensure that each server can connect to each other server on the network. For example, ensure that your firewall rules allow the servers to communicate over HTTPS and JMS.

Cluster connections create a JMS mesh, which facilitates JMS communication between servers in a clustered high-availability server configuration. See [Setting up high-availability clusters](../../com.udeploy.doc/topics/server_install_clustered.md#).

Cluster connections are required only if you have more than one server. Also, they facilitate communication only among servers; cluster connections are not used for agents or agent relays. Because the servers use the same database, you can create connections on any server; the other servers all have access to those connections.

**Note:** In version 6.2.3 and many prior versions, using network relays to reverse the direction of JMS communication through a firewall is deprecated. Beginning in version 6.2.3.1, network relays and cluster connections do not reverse the connection of JMS communication through firewalls. Instead, you must set your firewall to allow HTTPS and JMS connections from agent relays to the server.

1.   On any server in the cluster, click **Settings** \> **Network** \> **Add Server To Server Cluster**. The Connect Server To Server Cluster dialog box is displayed.
2.   Enter a name for the cluster connection. 
3.   In the **Host** field, enter the host name or IP address of the target server. 
4.   In the **Port** field, enter the JMS communication port of the target server. The default server JMS communication port number is 7918.
5.  Select the **Active** check box. 
6.  Click **Save**.
7.   On the same server, repeat the process to create a connection to each server in the cluster, including a connection that points to the current server itself. 
8.   Restart the targeted servers. If you create the cluster connections on server A, for example, restart servers B and C to ensure that they can communicate with one another.

The servers can now communicate via JMS.

If you have four HCL UrbanCode Deploy servers in a clustered high-availability configuration, on only one of the servers, create four cluster connections. One connection points to each server, including a connection to the server on which you create the connections. A JMS request from any agent or agent relay is routed to the appropriate HCL UrbanCode Deploy server by using the JMS mesh and these connections.

**Parent topic:** [Setting up high-availability clusters](../../com.udeploy.doc/topics/server_install_clustered.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

