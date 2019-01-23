# getSnapshotConfiguration

Get the list of configuration objects in a snapshot

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getSnapshotConfiguration [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

Related REST command: [Get the list of configuration objects in a snapshot](rest_cli_snapshot_getsnapshotconfiguration_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

