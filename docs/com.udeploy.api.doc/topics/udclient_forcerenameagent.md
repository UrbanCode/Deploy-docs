# forceRenameAgent

Rename an agent

Rename an agent. Use this command if running the agent configuration script in the agent bin directory is not convenient. Only the administrator can run this method.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  forceRenameAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent to rename|
|name|string|true|The new name for the agent|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  forceRenameAgent
  -agent Agent1
  -name NewAgentName
```

Related REST command: [Rename an agent](rest_cli_agentcli_rename_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

