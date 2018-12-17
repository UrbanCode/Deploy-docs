# createTeam

Create a team

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team|
|description|string|false|Description of the team|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createTeam
  -team MyNewTeam
  -description "MyNewTeamDescription"
```

## Example response

```
{
  "id": "769c2486-ed40-4a3a-ac52-faa33d30cfd5",
  "name": "MyNewTeam",
  "description": "MyNewTeamDescription",
  "isDeletable": true
}

```

Related REST command: [Create a team](rest_cli_team_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

