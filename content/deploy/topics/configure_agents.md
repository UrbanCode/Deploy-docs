# Agents and agent relay configuration {#configure_agents .concept}

After you install an agent for IBM® UrbanCode® Deploy, you can modify its configuration or create an agent relay to facilitate communication to remote relays.

To monitor the status of the relay and the agents that are connected to it, click **Resources** \> **Agent Relays**. This tab shows the number of active and offline agents that are connected to each relay, as shown in the following figure:

![Information about agent relays, including the number and state of connected agents](../../com.ibm.udeploy.install.doc/topics/../images/agentRelayInstall_a.gif)

For more information about an agent relay, in the **Name** column, click the relay.

-   **[Changing or updating the JRE of agents](../topics/jre_change_agent.md)**  
You can change the JRE of active agents by editing their configuration files.
-   **[Changing passwords for the agent relay keystores](../topics/keystore_agentrelay_change_password.md)**  
You can change the Java™ keystore passwords for the agent relay.
-   **[Caching artifacts on agent relays](../../com.ibm.udeploy.install.doc/topics/t_agent_relay_cache_setup.md)**  
Agent relays can cache downloaded artifacts. Caching artifacts in this way improves performance because agents retrieve artifacts from agent relays instead of from the server.
-   **[Agent security and communication](../topics/arch_agents.md)**  
Agents use SSL-secured JMS, WebSocket, HTTP, and HTTPS protocols to communicate with the server.
-   **[Web agents](../topics/web_agents.md)**  
Web agents use WebSocket and HTTP connections for communication. Web agents do not use JMS.
-   **[Migrating Agents to Web](../topics/mass_agent_migration.md)**  
Agent Configuration Templates allow you to migrate JMS agents on a server to Web agents with the ability to revert back to the original JMS configuration. This allows you to specify connection details for groups of agents.
-   **[Removing and reinstalling agents as Windows services](../topics/agent_service_windows.md)**  
If you installed an agent as a Windows™ service, you can remove and reinstall the service.
-   **[Managing agents remotely](../topics/agent_manageremote.md)**  
After an agent is installed, you can manage \(with the monitor process\) many of its features from the IBM UrbanCode Deploy web application.
-   **[Setting agent properties](../topics/agent_properties.md)**  
Agent properties store information that is relevant to a specific agent.
-   **[Creating and managing agent pools](../topics/resources_agentPools.md)**  
Similar to resource groups, agent pools help you organize and manage agents that are installed in different environments.

**Parent topic:** [Configuring](../topics/c_node_configuring.md)

