# Agent installation properties

The agent properties in the installed.properties file control details about the agent, including how it connects to the server.

|Property|Default value|Description|
|--------|-------------|-----------|
|agent.HttpFailoverHandler.disabled|`null`|If this property is set to anything other than `true`, the agent recreates its HTTP proxy connection when it receives JMS messages from a host other than the one configured in http.proxy.host. Setting this property to `true` disables this behavior.|
|agent.jms.disable\_full\_encryption|`false`|If this property is set to `true`, the agent does not use end-to-end encryption for the JMS protocol. See [Ensuring end-to-end JMS encryption](ssl_addl_security_2.md).|
|agentcomm.server.uri| ```
random:(wss://ucd1.example.com:7919,wss://ucd2.example.com:7919)
```

 |For Web agents, the WebSocket connection that is used to communicate with the server. The WebSocket secure URL must have the format `wss://host-or-ip:port`. Each server must have a unique URL, and every server in a HA cluster must be able to connect to this URL.|
|agentcomm.proxy.uri| ```
random:(http://relay1:20080,http://relay2:20080
```

 |For Web agents, the WebSocket connection that is used to communicate with an agent relay.|
|com.urbancode.shell.impersonation.unix.scriptLocation|None|The location to which the impersonation scripts are written before they are run on the agent. For example, to write scripts to the folder /opt/ibm/ucd/scripts, use this code:```
com.urbancode.shell.impersonation.unix.scriptLocation=/opt/ucd/scripts
```

|
|com.urbancode.shell.impersonation.unix.scriptMode|None|This property represents the file permissions to use for the scripts that are written for each impersonation step. For example, to set the file permissions to 0750, which means that the owner can read, write, and execute, and the group can read and execute but not write, use this code:```
com.urbancode.shell.impersonation.unix.scriptMode=0750
```

|
|com.urbancode.shell.impersonation.unix.scriptPostExecuteAction|None|With this property, you can specify a script to run after each step that uses impersonation. For example: ```
com.urbancode.shell.impersonation.unix.scriptPostExecuteAction=/opt/ucd/agent/bin/sudoPostAction.sh
```

|
|com.urbancode.shell.impersonation.unix.scriptPreExecuteAction|None|With this property, you can specify a script to run before each step that uses impersonation. For example: ```
com.urbancode.shell.impersonation.unix.scriptPreExecuteAction=/opt/ucd/agent/bin/sudoPreAction.sh
```

|
|java.home|None.|The location of the installation of Java™ to use.|
|locked/agent.brokerUrl|`failover\:(ah3\://hostname\:7918,ah3\://localhost\:7918)`|This property specifies the server or relay to connect to, in the form of a list of one or more ActiveMQ brokers. You do not specify this property manually at installation time; it is added automatically during installation or upgrade based on the values of the locked/agent.jms.remote.host and locked/agent.jms.remote.port properties. If you specify a value for this property as described in [Installing agents in silent mode](agent_install_silent.md) and install or upgrade the agent, the installation process overwrites the value. After the agent is installed, you can update this property. This property must list at least one server or agent relay. The property can contain only servers or only agent relays, not both. In a simple scenario, the property lists the server that the agent connects to, such as in the following example:

```
locked/agent.brokerUrl=failover\:(ah3\://ucd.example.com\:7918)
```

This property can refer to multiple relays or servers by separating them with commas. This property cannot refer to load balancers. It can refer to a DNS round robin that resolves to one or more agent relays.

**Note:** To assemble this property correctly, you must also specify hosts in the locked/agent.jms.remote.host property and the ports for those hosts in the locked/agent.jms.remote.port property. Each entry in the locked/agent.jms.remote.host property must have a matching value in the locked/agent.jms.remote.port, even if multiple brokers use the same port.

To configure the agent to contact other servers or agent relays in the case of a failover, see [Configuring agents for failover](configure_agent_failover.md).

For information on the format of this property, see [http://activemq.apache.org/failover-transport-reference.html](http://activemq.apache.org/failover-transport-reference.html).

|
|locked/agent.home|`/opt/urbancode/ucdagent`|The installation directory for the agent.|
|locked/agent.http.proxy.host|None.|The host name or IP address of the initial proxy connection, if a proxy is used. This information is used if the agent connects to an agent relay. This property cannot be the host name of a load balancer.If agent.HttpFailoverHandler.disabled is set to anything other than true, the agent can change to a new proxy without updating this property.

|
|locked/agent.http.proxy.port|20080|The HTTP proxy port of the agent relay, if used. See the information about the property locked/agent.http.proxy.host.|
|locked/agent.initial.teams|None.|Use this option to assign a team to your agent. The value to specify is the team name|
|locked/agent.jms.remote.host|`localhost`|The host name or IP address of the server or agent relay to which the agent connects.This property is used in installation and upgrades. When you install an agent silently, you specify this property in the silent installation file. The installation program uses this value to populate the locked/agent.brokerUrl property.

This property is not used on an installed agent. Instead, the locked/agent.brokerUrl property specifies the server or relay that the agent connects to.

|
|locked/agent.jms.remote.port|7918|For JMS agents, the port that the agent uses to connect to the server or agent relay. This property is used in installation and upgrades. When you install an agent silently, you specify this property in the silent installation file. The installation program uses this value to populate the locked/agent.brokerUrl property.

This property is not used on an installed agent. Instead, the locked/agent.brokerUrl property specifies the server or relay that the agent connects to.

**Note:** This property must have the same number of entries as the locked/agent.jms.remote.host property, even if some of the brokers use the same ports. When the agent is installed, the installation program checks that the locked/agent.jms.remote.host and locked/agent.jms.remote.port properties have the same number of entries. If they do not, the installation fails. When the agent is upgraded, if the locked/agent.brokerUrl property is not specified, the upgrade process recreates the locked/agent.brokerUrl property based on the locked/agent.jms.remote.host and locked/agent.jms.remote.port properties.

|
|locked/agent.keystore|/opt/urbancode/keys/common.keystore|The path to the agent keystore.|
|locked/agent.keystore.pwd|`changeit`|The agent keystore password.|
|locked/agent.mutual\_auth|`false`|Specify `true` to require mutual authentication between servers and agents. See [Configuring mutual authentication](ssl_mutual_auth.md).|
|locked/agent.name|`ucdagent`|The name of the agent. Agent names must be unique. You cannot change an agent name by editing this value. Rename agents in the graphical user interface by clicking the **Edit** icon that is associated with an agent in the resource tree.|
|locked/agent.service|`true`|Specify `true` to configure the agent to run as a service on Windows™.|
|locked/agent.service.name|`ucdagent`|The name of the agent service. This property applies only when the agent is installed as a service on Windows.|
|locked/agent.service.login|.\\\\localsystem|The service user account. The account must have the correct permissions to run a service. This property applies only when the agent is installed as a service on Windows.|
|locked/agent.service.password|`nopass`|The password that is associated with the service user. This property applies only when the agent is installed as a service on Windows.|
|locked/agent.service.autostart|`false`|Specify `true` to configure the agent to run automatically when Windows starts. This property applies only when the agent is installed as a service on Windows.|
|verify.server.identity|`false`|Specify `true` to configure the agent to reject self-signed certificates when connecting to the server. See [Enabling server identity verification](ssl_addl_security.md).|
|server.token| | An authentication token to be used to import z/OS component versions. The token is encrypted after the first time it is used.

 |
|server.url|`https://0.0.0.0:8443`|The web URL for the HCL UrbanCode Deploy server.|
|repository.type|`CODESTATION`| Specify `CODESTATION` to store versions in the HCL UrbanCode Deploy.

 Specify HFS to store versions in an HFS folder in the LPAR where the version is imported.

 For more information, see [Choosing a CodeStation and planning storage](codestation_choose_plan.md#).

 This property applies only when the agent is installed on IBM z/OS

 |

**Parent topic:** [Installing agents](../../com.udeploy.install.doc/topics/agent_install_ov.md)

