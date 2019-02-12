# deleteEnvironment

Delete an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteEnvironment [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|deleteAttachedResources|boolean|false|Specify true to delete all resources in this environment, including all subresources \(Optional\)|
|deleteCloudInstances|boolean|false|Specify true to delete any associated instances in the cloud provider; this parameter is valid only for environments that were created dynamically along with the environment \(Optional\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteEnvironment 
  -application JPetStore 
  -environment NewEnvironment
```

Related REST command: [Delete an environment](rest_cli_environment_deleteenvironment_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

