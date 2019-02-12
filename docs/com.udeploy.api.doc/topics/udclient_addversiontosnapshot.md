# addVersionToSnapshot

Add a component version to a snapshot

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addVersionToSnapshot [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|
|version|string|true|Name or ID of the component version|
|component|string|false|Name of the component; this value is required if you specify the component name instead of ID|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addVersionToSnapshot
  -application MyApplication
  -component MyComponent
  -snapshot MySnapshot
  -version 1.2

```

Related REST command: [Add a component version to a snapshot](rest_cli_snapshot_addversiontosnapshot_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

