# Lock a snapshot's configuration

This command locks the configuration included in a snapshot. This prevents the snapshot from being affected by any future changes to the relevant configuration and also prevents users from manually changing which configuration the snapshot is using. This cannot be reversed.

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/lockSnapshotConfiguration?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

Related CLI command: [lockSnapshotConfiguration](udclient_locksnapshotconfiguration.md).

**Parent topic:** [snapshot resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_snapshot.md)

