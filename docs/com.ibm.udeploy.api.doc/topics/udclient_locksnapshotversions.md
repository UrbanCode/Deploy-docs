# lockSnapshotVersions

Lock a snapshot's version list

This command locks the list of component versions included in a snapshot. This cannot be reversed and prevents any future changes to the list of versions included in the snapshot.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  lockSnapshotVersions [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

Related REST command: [Lock a snapshot's version list](rest_cli_snapshot_locksnapshotversions_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

