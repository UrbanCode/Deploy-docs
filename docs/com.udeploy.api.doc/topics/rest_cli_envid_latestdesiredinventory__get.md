# Get the latest desired inventory for an environment.

This command returns a JSON array of all of the desired inventory for an environment.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/{environmentId}/latestDesiredInventory/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|Name or ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getLatestDesiredInventory](udclient_getlatestdesiredinventory.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

