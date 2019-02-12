# Get information about all component process requests

This command returns a JSON representation of a list of up to 100 component process requests at a time.

## Request

```
GET https://{hostname}:{port}
    /cli/componentProcessRequest/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|submittedAfter|long|false|Time value that marks the oldest CPR we want to retrieve.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getComponentProcessRequests](udclient_getcomponentprocessrequests.md).

**Parent topic:** [componentProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_componentprocessrequest.md)

