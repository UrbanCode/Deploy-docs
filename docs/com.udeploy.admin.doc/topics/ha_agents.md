# High-availability agent communication

Agents communicate with the server over JMS and HTTP or HTTPS. These modes of communication are handled differently in a high availability scenario.

## JMS communication

JMS communications is subscription-based. All agents subscribe to all topics and filter the list with their agent ID. For this reason, assigning unique IDs to agents is required.

For JMS-based communications, agents can be configured in two ways:

-   Approach 1: Agents are individually configured for failover. If an agent fails to connect to a server or agent relay, the agent connects to failover servers or agent relays. See [Configuring agents for failover](../../com.udeploy.install.doc/topics/configure_agent_failover.md#).
-   Approach 2: Agents connect to a single agent relay that is configured for failover. See [Configuring agent relays for failover](../../com.udeploy.install.doc/topics/configure_relay_failover.md#).

Approach 1 works best because it allows for you to configure stable failover configurations in ActiveMQ.

**Note:** Do not configure a load balancer to distribute requests for the agent communication JMS port. To ensure agent and agent relay availability, configure them for failover.

## HTTP or HTTPS communication

A standard load balancer handles HTTP or HTTPS server-agent communications. Authentication is run on every request; any server can run validation for any request. You configure HTTP or HTTPS server-agent communication when you configure your cluster of servers. See [Setting up clusters of servers](../../com.udeploy.doc/topics/ha_config_server.md#).

In case of server failure, user-server authentication must be redone unless the ‘remember me’ cookie is used.

**Parent topic:** [High availability overview](../../com.udeploy.doc/topics/ha_overview.md)

**Parent topic:** [Managing security](../../com.udeploy.admin.doc/topics/security_ch.md)

