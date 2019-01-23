# removeProcessFromTeam

Remove a process from a team

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeProcessFromTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|process|string|true|Name or ID of the process.|
|team|string|true|Name or ID of the team.|
|type|string|false|Name of the security type to use; the default is Standard Process.|

Related REST command: [Remove a process from a team](rest_cli_process_teams_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

