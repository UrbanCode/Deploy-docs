# addAgentToPool

Add an agent to an agent pool

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addAgentToPool [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|pool|string|true|Name or ID of the agent pool|
|agent|string|true|Name or ID of the agent|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addAgentToPool
  -agent Agent1
  -pool Pool1
```

Related REST command: [Add an agent to an agent pool](rest_cli_agentpool_addagenttopool_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

