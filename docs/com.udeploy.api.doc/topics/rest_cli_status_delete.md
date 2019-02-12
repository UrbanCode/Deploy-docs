# Delete a status

## Request

```
DELETE https://{hostname}:{port}
    /cli/status?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|false|Type of status \(inventory, version, or snapshot\); this parameter is required you specify the name of the status instead of the ID|
|status|string|true|Name or ID of the status|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [deleteStatus](udclient_deletestatus.md).

**Parent topic:** [status resource](../../com.udeploy.api.doc/topics/rest_cli_status.md)

