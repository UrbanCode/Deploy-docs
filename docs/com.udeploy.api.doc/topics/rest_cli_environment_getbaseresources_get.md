# Get all base resources for an environment

This command returns a listing of all resources added as base resources to an environment.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/getBaseResources?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

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

Related CLI command: [getEnvironmentBaseResources](udclient_getenvironmentbaseresources.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

