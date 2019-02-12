# removeApplicationFromTeam

Remove an application from a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  removeApplicationFromTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application.|
|team|string|true|Name or ID of the team.|
|type|string|false|Name of the security type to use; the default is Standard Application.|

Related REST command: [Remove an application from a team](rest_cli_application_teams_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

