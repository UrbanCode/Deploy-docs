# Configuring agent relays for failover

To configure agent relays for failover, you specify two or more target servers for the agent relay to use. If one of the servers fails, the agent relay switches to another server from the list.

You must upgrade an agent relay to version 6.1.1.1 or later to configure it for failover.

If you did not configure the agent relay for failover when you installed the relay, you can also configure it for failover by modifying its properties.

1.  Open the /agent-relay-install/conf/agentrelay.properties file. 
2.   In the `agentrelay.jms_proxy.servers` parameter, provide a list of server locations. This list can include only servers, not other agent relays. The configuration syntax is `server\_IP\_or\_hostname\:JMS_port`. Separate each entry with a comma. An example parameter that specifies two servers might resemble the following code: `agentrelay.jms_proxy.servers=newyork-server.example.com\:7918,losangeles-server.example.com\:7918`.

**Parent topic:** [Configuring](../../com.ibm.udeploy.doc/topics/c_node_configuring.md)

