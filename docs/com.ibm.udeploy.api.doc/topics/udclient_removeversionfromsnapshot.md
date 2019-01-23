# removeVersionFromSnapshot

Remove a component version from a snapshot

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeVersionFromSnapshot [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|
|version|string|true|Name or ID of the component version|
|component|string|false|Name of the component; this value is required if you specify the component name instead of ID|

Related REST command: [Remove a component version from a snapshot](rest_cli_snapshot_removeversionfromsnapshot_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

