# getVersionLinks

List links on a version

This command lists all links that are associated with a specified component version.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getVersionLinks [parameters]
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
  getVersionLinks 
  -component JPetStore-APP 
  -version 1.0
```

## Example response

```
[
  {
    "name": "Link to MyCompany example web site",
    "value": "http://mycompany.example.com"
  },
  {
    "name": "Link to IBM web site",
    "value": "http://www.ibm.com"
  }
]
```

Related REST command: [List links on a version](rest_cli_version_getlinks_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

