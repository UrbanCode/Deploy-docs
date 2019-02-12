# lockSnapshotConfiguration

Lock a snapshot's configuration

This command locks the configuration included in a snapshot. This prevents the snapshot from being affected by any future changes to the relevant configuration and also prevents users from manually changing which configuration the snapshot is using. This cannot be reversed.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  lockSnapshotConfiguration [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

Related REST command: [Lock a snapshot's configuration](rest_cli_snapshot_locksnapshotconfiguration_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

