# removeAgentPoolFromTeam

Remove an agent pool from a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  removeAgentPoolFromTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agentPool|string|true|Name or ID of the agent pool|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard agent pool".|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeAgentPoolFromTeam
  -agentPool MyAgentPool
  -team MyTeam
```

Related REST command: [Remove an agent pool from a team](rest_cli_agentpool_teams_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

