# getVersionLink

Get a link on a component version

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getVersionLink [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|linkName|string|true|Name of the link|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getVersionLink 
  -component JPetStore-APP 
  -version 1.0 
  -linkName "Link to IBM web site"
```

## Example response

```
{
  "name": "Link to IBM web site",
  "value": "http://www.ibm.com"
}
```

Related REST command: [Get a link on a component version](rest_cli_version_getlink_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

