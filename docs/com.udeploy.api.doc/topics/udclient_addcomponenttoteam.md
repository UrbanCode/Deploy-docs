# addComponentToTeam

Add a component to a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addComponentToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Component".|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addComponentToTeam
  -component JPetStore-APP
  -team MyTeam
```

Related REST command: [Add a component to a team](rest_cli_component_teams_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

