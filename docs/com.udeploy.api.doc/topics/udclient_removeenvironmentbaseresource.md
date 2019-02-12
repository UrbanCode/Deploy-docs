# removeEnvironmentBaseResource

Remove a base resource from an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  removeEnvironmentBaseResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|
|resource|string|true|Path or ID of the resource to remove|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeEnvironmentBaseResource 
  -application JPetStore 
  -environment "Tutorial environment 1" 
  -resource "/JPetStore agents/Tutorial agent 1"
```

Related REST command: [Remove a base resource from an environment](rest_cli_environment_removebaseresource_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

