# deleteAgent

Delete an agent

Agents should be shut down before deletion.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  deleteAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteAgent
  -agent Agent1
```

Related REST command: [Delete an agent](rest_cli_agentcli_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

