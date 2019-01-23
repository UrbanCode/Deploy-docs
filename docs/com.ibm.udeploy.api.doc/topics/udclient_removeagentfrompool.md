# removeAgentFromPool

Remove an agent from an agent pool

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeAgentFromPool [parameters]
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
  removeAgentFromPool
  -pool Pool1
  -agent Agent1
```

Related REST command: [Remove an agent from an agent pool](rest_cli_agentpool_removeagentfrompool_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

