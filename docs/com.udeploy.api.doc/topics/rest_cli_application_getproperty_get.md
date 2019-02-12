# Get the value of a custom property on a application

## Request

```
GET https://{hostname}:{port}
    /cli/application/getProperty?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|name|string|true|Name of the property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

Related CLI command: [getApplicationProperty](udclient_getapplicationproperty.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

