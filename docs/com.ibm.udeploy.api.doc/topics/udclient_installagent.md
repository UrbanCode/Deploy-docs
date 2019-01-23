# installAgent

Install an agent

This command installs an agent over SSH.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  installAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the agent resource|
|host|string|true|Host name or IP address of the system to install the agent on|
|port|int|true|SSH port of the agent system; the default port is 22|
|sshUsername|string|true|SSH user name to use to connect to the agent system|
|sshPassword|string|false|SSH password for the agent system; leave blank to use public key authentication instead|
|installDir|string|true|Installation directory for the agent|
|javaHomePath|string|true|Path to Java on the agent system|
|tempDirPath|string|true|Path to directory to install from on the agent system|
|serverHost|string|true|Host name or IP address of the UrbanCode Deploy server or agent relay that the agent connects to|
|serverPort|int|true|Agent communication port of the UrbanCode Deploy server \(7918\) or agent relay \(7916\) the agent connects to|
|relayWebPort|int|false|HTTP proxy port of the agent relay, if the agent is connecting to an agent relay; the default is 20080|
|mutualAuth|boolean|false|Specify true to enforce certificate validation for mutual authentication|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  installAgent
  -name NewAgent
  -host agenthost.example.com
  -port 22
  -sshUsername root
  -sshPassword 12345
  -installDir /opt/ibm-ucd/agent
  -javaHomePath /usr/lib/java
  -tempDirPath /tmp
  -serverHost ucdeploy.example.com
  -serverPort 7918
```

Related REST command: [Install an agent](rest_cli_sshinstallagent_installnewagent_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

