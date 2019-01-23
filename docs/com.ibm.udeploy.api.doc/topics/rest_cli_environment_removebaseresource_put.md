# Remove a base resource from an environment

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/removeBaseResource?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|
|resource|string|true|Path or ID of the resource to remove|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [removeEnvironmentBaseResource](udclient_removeenvironmentbaseresource.md).

**Parent topic:** [environment resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment.md)

