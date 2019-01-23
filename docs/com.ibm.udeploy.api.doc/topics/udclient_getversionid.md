# getVersionId

Get a version ID

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getVersionId [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getVersionId
  -component MyComponent
  -version 1.2
```

## Example response

```
1a53a4a6-bfcd-4014-a0ab-83f97077a4d4
```

Related REST command: [Get a version ID](rest_cli_version_getversionid_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

