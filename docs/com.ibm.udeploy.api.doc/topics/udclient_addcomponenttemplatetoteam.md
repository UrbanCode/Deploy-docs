# addComponentTemplateToTeam

Add a component template to a team

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addComponentTemplateToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|componentTemplate|string|true|Name or ID of the component template|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Component Template".|

Related REST command: [Add a component template to a team](rest_cli_componenttemplate_teams_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

