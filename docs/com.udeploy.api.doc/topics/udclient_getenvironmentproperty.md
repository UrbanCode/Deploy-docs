# getEnvironmentProperty

Get the value of a custom property on an environment.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getEnvironmentProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getEnvironmentProperty 
  -application JPetStore 
  -environment "Tutorial environment 1" 
  -name tomcat.start
```

Related REST command: [Get the value of a custom property on an environment.](rest_cli_environment_getproperty_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

