# addVersionLink

Add a link on a version

This command adds an external link on the specified component version.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addVersionLink [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|linkName|string|true|Name of the link to add|
|link|string|true|Value of the link to add|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addVersionLink 
  -component JPetStore-APP 
  -version 1.0 
  -linkName "Link to IBM web site" 
  -link http://www.ibm.com
```

Related REST command: [Add a link on a version](rest_cli_version_addlink_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

