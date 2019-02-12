# addApplicationToTeam

Add an application to a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addApplicationToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Application".|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addApplicationToTeam
  -application JPetStore
  -team MyTeam
```

Related REST command: [Add an application to a team](rest_cli_application_teams_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

