# addEnvironmentToTeam

Add an environment to a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addEnvironmentToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|environment|string|true|Name or ID of the environment|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Application".|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addEnvironmentToTeam
  -application MyApplication
  -environment MyEnvironment
  -team MyTeam
```

Related REST command: [Add an environment to a team](rest_cli_environment_teams_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

