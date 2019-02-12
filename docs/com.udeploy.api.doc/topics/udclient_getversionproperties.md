# getVersionProperties

List the properties on a component version

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getVersionProperties [parameters]
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
  getVersionProperties
  -component JPetStore-APP
  -version 1.0
```

## Example response

```
[
  {
    "id": "33528ab5-a7be-46cb-9f0c-916a42bd2f62",
    "name": "Prop1",
    "value": "value1",
    "description": "",
    "secure": false
  },
  {
    "id": "92339074-ab59-4fe3-936f-9ceec16ce5e6",
    "name": "Prop2",
    "value": "value1",
    "description": "",
    "secure": false
  }
]
```

Related REST command: [List the properties on a component version](rest_cli_version_versionproperties_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

