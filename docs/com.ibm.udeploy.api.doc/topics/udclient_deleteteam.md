# deleteTeam

Delete a team

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  deleteTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteTeam
  -team MyNewTeam
```

Related REST command: [Delete a team](rest_cli_team_delete_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

