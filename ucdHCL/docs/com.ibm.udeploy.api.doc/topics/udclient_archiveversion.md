# archiveVersion

Archive the given versions of a component

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  archiveVersion [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|version|string|true|Name or ID of the version\(s\) to be archived. This option can be repeated to archive multiple versions.|
|path|string|false|Archive path. An absolute path which overrides the System's archive path|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  archiveVersion
  -component MyComponent
  -version 1.0
  -version 1.2
  -version 1.3
```

Related REST command: [Archive the given versions of a component](rest_cli_version_archiveversion_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

