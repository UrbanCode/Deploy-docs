# Get the value of a custom property on an environment.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/getProperty?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

Related CLI command: [getEnvironmentProperty](udclient_getenvironmentproperty.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

