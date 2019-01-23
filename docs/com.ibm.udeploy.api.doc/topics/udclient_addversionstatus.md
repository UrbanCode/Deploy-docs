# addVersionStatus

Add a status to a version

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addVersionStatus [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|status|string|true|Name of the status to apply|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addVersionStatus
  -component JPetStore-APP
  -version 1.0
  -status Approved
```

Related REST command: [Add a status to a version](rest_cli_version_addstatus_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

