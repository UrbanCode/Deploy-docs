# Get all of the latest desired inventory for an environment.

This command returns a JSON array of all of the desired inventory for an environment. It optionally groups the desired inventory by component.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/{environmentId}/latestDesiredInventory/{groupVersions}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|Name or ID of the environment|
|groupVersions|boolean|true|True if the versions should be grouped by component.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getAllLatestDesiredInventory](udclient_getalllatestdesiredinventory.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

