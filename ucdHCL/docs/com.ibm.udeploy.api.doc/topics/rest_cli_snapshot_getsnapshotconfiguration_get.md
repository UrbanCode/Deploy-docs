# Get the list of configuration objects in a snapshot

## Request

```
GET https://{hostname}:{port}
    /cli/snapshot/getSnapshotConfiguration?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getSnapshotConfiguration](udclient_getsnapshotconfiguration.md).

**Parent topic:** [snapshot resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_snapshot.md)

