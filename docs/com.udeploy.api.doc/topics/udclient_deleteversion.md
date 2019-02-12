# deleteVersion

Delete a version from a component

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteVersion [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component|
|version|string|true|Name or ID of the version\(s\) to be deleted. This option can be repeated to delete multiple versions.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteVersion
  -component MyComponent
  -version 1.0
```

Related REST command: [Delete a version from a component](rest_cli_version_deleteversion_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

