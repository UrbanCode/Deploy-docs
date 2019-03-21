# Configuring

Learn how to configure settings in HCL® UrbanCode™ Deploy elements and communication between the elements.

-   **[High availability and failover](../topics/ha_config_ov.md)**  
You can configure clustered HCL UrbanCode Deploy servers, blueprint design servers, and agents for high availability. You can also configure agents and agent relays for failover.
-   **[Setting up high-availability clusters](../topics/server_install_clustered.md)**  
To configure a high-availability cluster, you store shared files on network storage. Then, you configure multiple servers, set each server to access the same files and database, and configure a load balancer to distribute the traffic between the servers.
-   **[Adding cold standby servers](../../com.udeploy.install.doc/topics/server_install_cold.md)**  
You can add cold standby servers to serve as a backup server or for disaster recovery. You must start the secondary server or servers when the active server fails, and network traffic is routed to the secondary servers.
-   **[Configuring agents for failover](../../com.udeploy.install.doc/topics/configure_agent_failover.md)**  
To configure agents for failover, you specify two or more target servers for the agent to use. If one of the servers fails, the agent switches to another server from the list.
-   **[Configuring agent relays for failover](../../com.udeploy.install.doc/topics/configure_relay_failover.md)**  
To configure agent relays for failover, you specify two or more target servers for the agent relay to use. If one of the servers fails, the agent relay switches to another server from the list.
-   **[Server settings and configuration](../topics/settings_ch.md)**  
After you install HCL UrbanCode Deploy, you can modify the server configuration and configure more options.
-   **[Setting user preferences](../../com.udeploy.admin.doc/topics/prefs_ov.md)**  
Each user can specify display options for the server, including the language for the server and how the server shows times and dates.
-   **[Agents and agent relay configuration](../topics/configure_agents.md)**  
After you install an agent for HCL UrbanCode Deploy, you can modify its configuration or create an agent relay to facilitate communication to remote relays.
-   **[License management](../topics/licenseManage.md)**  
HCL UrbanCode Deploy provides a 60-day license-free evaluation period. To use all product features after the evaluation period, you must have a license.
-   **[HCL License management](../topics/licenseManageHCL.md)**  
 Once you purchase HCL UrbanCode Deploy you will receive notification of access to the HCL License Portal via email. You can manage your licenses associated with your order and download the software for installation.
-   **[Setting up the wizard for new users](../topics/config_wizard.md)**  
HCL UrbanCode Deploy includes a wizard to help users become familiar with the procedures and steps in creating a deployment. Some configuration is required before the wizard can be used.
-   **[Configuring SSL on Apache Tomcat and LDAP servers](../topics/ssl_config.md)**  
The steps for configuring secure HTTP connections with the HCL UrbanCode Deploy server are similar to the steps for any Java™ Platform, Enterprise Edition server.
-   **[SSL configuration](../topics/SSLinstall.md)**  
With Secure Sockets Layer \(SSL\) technology, clients and servers can communicate securely by encrypting all communications. Data is encrypted before it is sent and decrypted by the recipient. This communication cannot be deciphered or modified by third-parties. In addition to encryption, SSL can also support authentication.

