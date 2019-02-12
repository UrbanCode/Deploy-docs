# Converting a stand-alone server to high availability

You can convert an HCL® UrbanCode™ Deploy server into the first node of a high-availability cluster.

-   Each server in the cluster must run the same version of HCL UrbanCode Deploy.
-   Ensure that each server can connect to each other server on the network. For example, ensure that your firewall rules allow the servers to communicate over HTTPS and JMS.

To convert a stand-alone server to the first node in a clustered configuration, you first move CodeStation to shared network storage, and then modify the server settings for multi-server operation.

1.   Move CodeStation to a shared storage location with a fast network connection. Because each cluster server must access the same configuration files, each server must have access to this network storage. See [Relocating CodeStation](arch_relocate_codestation.md).
2.   Install a load balancer to send requests to the servers. The load balancer must be able to forward requests to the HTTP and HTTPS ports for the servers. For more information, see the documentation for your load balancer.

    **Note:** Do not configure a load balancer to distribute requests for the agent JMS communication port. To ensure agent and agent relay availability, configure them for failover.

    **Important:** You must configure the load balancer for session persistence, also known as session affinity.

3.   Stop of the server. 
4.   Add the following line of code to the install\_folder/conf/server/installed.properties file: 

    ```
    com.urbancode.ds.UDeployServer.multiserver=true
    ```

5.   Start the server. 
6.   On the new cluster server, click **Settings** \> **System Settings**, and set the **External Agent URL** and the **External User URL** to the URL for the load balancer. 
7.   Configure the license server for high availability. For information, see the Rational® Common Licensing documentation: [http://www-01.ibm.com/support/knowledgecenter/SSSTWP](http://www-01.ibm.com/support/knowledgecenter/SSSTWP). For high availability options for the license server, see [http://www-01.ibm.com/support/docview.wss?uid=swg27036356&aid=1](http://www-01.ibm.com/support/docview.wss?uid=swg27036356&aid=1).

After you configure the server and the load balancer, you can add nodes to the cluster.

-   Add new servers to the cluster. See [Adding servers to clusters](ha_add_server.md).
-   Configure agents and agent relays for failover. See [Configuring agents for failover](../../com.udeploy.install.doc/topics/configure_agent_failover.md) and [Configuring agent relays for failover](../../com.udeploy.install.doc/topics/configure_relay_failover.md).

**Parent topic:** [Setting up high-availability clusters](../topics/server_install_clustered.md)

