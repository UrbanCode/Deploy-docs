# getEnvironmentBaseResources

Get all base resources for an environment

This command returns a listing of all resources added as base resources to an environment.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getEnvironmentBaseResources [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getEnvironmentBaseResources 
  -application JPetStore 
  -environment "Tutorial environment 1"
```

## Example response

```
[
  {
    "id": "4db385d8-34bb-4625-8e62-c627175a2cf7",
    "name": "Tutorial agent 1",
    "path": "/JPetStore agents/Tutorial agent 1",
    "active": true,
    "description": "",
    "inheritTeam": true,
    "impersonationPassword": "****",
    "impersonationUseSudo": false,
    "impersonationForce": false,
    "type": "agent",
    "status": "ONLINE",
    "hasAgent": true,
    "tags": [
    ]
  }
]
```

Related REST command: [Get all base resources for an environment](rest_cli_environment_getbaseresources_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

