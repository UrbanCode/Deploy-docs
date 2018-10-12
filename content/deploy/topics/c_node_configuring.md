# Configuring {#Configuring .concept}

Learn how to configure settings in IBM® UrbanCode® Deploy elements and communication between the elements.

-   **[High availability and failover](../topics/ha_config_ov.md)**  
You can configure clustered IBM UrbanCode Deploy servers, blueprint design servers, and agents for high availability. You can also configure agents and agent relays for failover.
-   **[Setting up high-availability clusters](../topics/server_install_clustered.md)**  
To configure a high-availability cluster, you store shared files on network storage. Then, you configure multiple servers, set each server to access the same files and database, and configure a load balancer to distribute the traffic between the servers.
-   **[Adding cold standby servers](../../com.ibm.udeploy.install.doc/topics/server_install_cold.md)**  
You can add cold standby servers to serve as a backup server or for disaster recovery. You must start the secondary server or servers when the active server fails, and network traffic is routed to the secondary servers.
-   **[Configuring disaster recovery for the blueprint design server](../../com.ibm.edt.doc/topics/dr_config_bds.md)**  
You can configure the blueprint design server and engine for disaster recovery by adding cold standby servers to serve as backup servers. You must start the secondary server or servers when the active server fails, and network traffic is routed to the secondary servers.
-   **[Configuring agents for failover](../../com.ibm.udeploy.install.doc/topics/configure_agent_failover.md)**  
To configure agents for failover, you specify two or more target servers for the agent to use. If one of the servers fails, the agent switches to another server from the list.
-   **[Configuring agent relays for failover](../../com.ibm.udeploy.install.doc/topics/configure_relay_failover.md)**  
To configure agent relays for failover, you specify two or more target servers for the agent relay to use. If one of the servers fails, the agent relay switches to another server from the list.
-   **[Server settings and configuration](../topics/settings_ch.md)**  
After you install IBM UrbanCode Deploy, you can modify the server configuration and configure more options.
-   **[Setting user preferences](../../com.ibm.udeploy.admin.doc/topics/prefs_ov.md)**  
Each user can specify display options for the server, including the language for the server and how the server shows times and dates.
-   **[Blueprint design server configuration](../../com.ibm.edt.doc/topics/c_node_administering_bds.md)**  
Learn how to configure the blueprint design server.
-   **[Estimating the cost for cloud environments](../../com.ibm.edt.doc/topics/cost_ov.md)**  
You can specify cost centers for cloud systems and for IBM UrbanCode Deploy components. Then, the blueprint design server estimates the cost of new environments by using that information.
-   **[Adding blueprint design servers to clusters](../../com.ibm.edt.doc/topics/ha_add_bds.md)**  
To add a blueprint design server to a cluster, connect it to the shared database and network storage. Then, configure the load balancer to send traffic to it.
-   **[Adding engines to clusters](../../com.ibm.edt.doc/topics/ha_add_engine.md)**  
To add an engine to a cluster, connect it to the shared database. Then, configure the load balancer to send traffic to it.
-   **[Setting up clusters of blueprint design servers](../../com.ibm.edt.doc/topics/ha_config_bds.md)**  
You can set up clusters of blueprint design servers for a high-availability configuration. As with setting up clusters of servers, you store shared files on a system and set multiple blueprint design servers to use those files.
-   **[Setting up clusters of engines](../../com.ibm.edt.doc/topics/ha_config_engine.md)**  
To set up clusters of engines, you store shared files on a system and set multiple engines to use those files.
-   **[Agents and agent relay configuration](../topics/configure_agents.md)**  
After you install an agent for IBM UrbanCode Deploy, you can modify its configuration or create an agent relay to facilitate communication to remote relays.
-   **[License management](../topics/licenseManage.md)**  
IBM UrbanCode Deploy provides a 60-day license-free evaluation period. To use all product features after the evaluation period, you must have a license.
-   **[Setting up the wizard for new users](../topics/config_wizard.md)**  
IBM UrbanCode Deploy includes a wizard to help users become familiar with the procedures and steps in creating a deployment. Some configuration is required before the wizard can be used.
-   **[Configuring SSL on Apache Tomcat and LDAP servers](../topics/ssl_config.md)**  
The steps for configuring secure HTTP connections with the IBM UrbanCode Deploy server are similar to the steps for any Java™ Platform, Enterprise Edition server.
-   **[SSL configuration](../topics/SSLinstall.md)**  
With Secure Sockets Layer \(SSL\) technology, clients and servers can communicate securely by encrypting all communications. Data is encrypted before it is sent and decrypted by the recipient. This communication cannot be deciphered or modified by third-parties. In addition to encryption, SSL can also support authentication.

