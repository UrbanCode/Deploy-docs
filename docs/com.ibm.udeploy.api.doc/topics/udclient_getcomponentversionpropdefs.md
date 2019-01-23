# getComponentVersionPropDefs

List the version property definitions for a component

These properties are available to each version of the component.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentVersionPropDefs [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentVersionPropDefs 
  -component JPetStore-APP
```

## Example response

```
[
  {
    "id": "870bc2f5-55e2-4cb9-b3ab-f750688754b9",
    "name": "Prop1",
    "label": "Prop1",
    "pattern": "",
    "type": "CHECKBOX",
    "value": "true",
    "required": false,
    "description": ""
  },
  {
    "id": "ee02cbf0-9fc9-465e-a37f-754c40222d0d",
    "name": "Prop2",
    "label": "",
    "pattern": "",
    "type": "TEXT",
    "value": "prop2",
    "required": false,
    "description": ""
  }
]
```

Related REST command: [List the version property definitions for a component](rest_cli_version_versionpropdefs_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

