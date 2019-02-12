# updateTeam

Update a team

Specify the team name in the 'team' parameter and use the 'name' and 'description' parameters to specify the desired changes.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  updateTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team to be changed|
|name|string|false|New name of the team|
|description|string|false|New description of the team|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  updateTeam
  -team MyNewTeam
  -name ADifferentTeamName
  -description "ADifferentTeamDescription"
```

Related REST command: [Update a team](rest_cli_team_update_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

