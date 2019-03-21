# Get resource tree for an environment

## Request

```
GET https://{hostname}:{port}
    /cli/environment/getEnvironmentResourceTree?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application. This is required when using environment name.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getEnvironmentResourceTree](udclient_getenvironmentresourcetree.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

