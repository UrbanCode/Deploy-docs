# Remove a component version from a snapshot

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/removeVersionFromSnapshot?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|
|version|string|true|Name or ID of the component version|
|component|string|false|Name of the component; this value is required if you specify the component name instead of ID|

Related CLI command: [removeVersionFromSnapshot](udclient_removeversionfromsnapshot.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

