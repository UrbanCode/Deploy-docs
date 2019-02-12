# Get information about a specific application process request

This command retrieves a specific application process request by id.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcessRequest/info/{requestID}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|requestID|string|true|The ID of the application process request.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getApplicationProcessRequest](udclient_getapplicationprocessrequest.md).

**Parent topic:** [applicationProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

