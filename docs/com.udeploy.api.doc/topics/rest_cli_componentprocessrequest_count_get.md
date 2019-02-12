# Get the number of component process requests submitted after a certain time

This command returns a count of all the component process requests submitted after a certain time.

## Request

```
GET https://{hostname}:{port}
    /cli/componentProcessRequest/count?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|submittedAfter|long|false|A timestamp, in milliseconds from the UNIX epoch. If you specify this parameter, the server counts all CPRs that were created after the specified timestamp.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getComponentProcessRequestCount](udclient_getcomponentprocessrequestcount.md).

**Parent topic:** [componentProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_componentprocessrequest.md)

