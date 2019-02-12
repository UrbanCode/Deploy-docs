# addEnvironmentBaseResource

Add a base resource to an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addEnvironmentBaseResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|
|resource|string|true|Path or ID of the resource to add|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addEnvironmentBaseResource
  -application MyApplication
  -environment Environment1
  -resource /agents/agent1
```

Related REST command: [Add a base resource to an environment](rest_cli_environment_addbaseresource_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

