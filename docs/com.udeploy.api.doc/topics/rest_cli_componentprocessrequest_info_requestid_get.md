# Get information about a specific component process request

Generally used as an endpoint to retrieve APRs that were scheduled in advance.

## Request

```
GET https://{hostname}:{port}
    /cli/componentProcessRequest/info/{requestID}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|requestID|string|true|The ID of the component process request.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getComponentProcessRequest](udclient_getcomponentprocessrequest.md).

**Parent topic:** [componentProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_componentprocessrequest.md)

