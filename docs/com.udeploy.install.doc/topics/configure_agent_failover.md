# Configuring agents for failover

To configure agents for failover, you specify two or more target servers for the agent to use. If one of the servers fails, the agent switches to another server from the list.

If you did not configure the agent for failover when you installed the agent, you can also configure it for failover by modifying its properties.

An agent that is configured for failover has a list of servers or agent relays to contact. If one server or agent relay is not available, the agent tries other servers or agent relays in the list.

**Restriction:** The failover list must contain only servers or only agent relays. An agent can not have both servers and agent relays in its failover list.

1.   Open the /agent-install/conf/agent/installed.properties file. 
2.   In the `locked/agent.brokerUrl=failover\:` parameter, provide a list of server locations or agent relay locations. This parameter can contain servers or agent relays, but not both. The agent configuration syntax is `IP\_or\_hostname\:JMS_port`. Separate each agent relay or server with a comma. When the agent starts, it selects one server or agent relay at random to use. If that server or agent relay fails, the agent selects a different server or agent relay from the list. The agent continues to use the server or agent relay until that server or agent relay fails. An example parameter that specifies two agent relays might resemble the following code: `locked/agent.brokerUrl=failover\:(ah3\://newyork-relay-server.example.com\:7916,ah3\://losangeles-relay-server.example.com\:7916)`.
3.   To make the agent use the servers or agent relays sequentially, append the code `?randomize=false` to the `locked/agent.brokerUrl=failover\:` parameter. By default, the agent uses entries in the list at random, including when it first starts. If you specify `?randomize=false`, the agent uses entries in the list in order, starting from the first entry. In either case, the agent continues to use the current server or agent relay until it fails, and then the agent switches to another entry in the list. For example, the parameter might look like the following code:`locked/agent.brokerUrl=failover\:(ah3\://newyork-relay-server.example.com\:7916,ah3\://losangeles-relay-server.example.com\:7916)?randomize=false` 
4.   List the host names or IP addresses of the agent relays or servers in the agent.jms.remote.host property, separated by commas. 
5.   List the agent communication port numbers of the agent relays or servers in the agent.jms.remote.port property. For example, if the agent.jms.remote.host property listed two servers and both servers use port 7916 for agent communication, the agent.jms.remote.port looks like this:

    ```
    agent.jms.remote.port=7916,7916
    ```

    Each agent relay or server that is listed in the agent.jms.remote.host must have a corresponding port in the agent.jms.remote.port property, even if the port numbers are the same as other agent relays or servers.


**Parent topic:** [Configuring](../../com.udeploy.doc/topics/c_node_configuring.md)

