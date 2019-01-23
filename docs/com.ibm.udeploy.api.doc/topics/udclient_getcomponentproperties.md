# getComponentProperties

Get values for component properties

This command returns all component properties.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentProperties [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentProperties
  -component JPetStore-APP
```

## Example response

```
[
  {
    "id": "3702f391-09e1-4550-903a-d5ae286c94aa",
    "name": "Prop1",
    "value": "value1",
    "description": "",
    "secure": false
  }
]
```

Related REST command: [Get values for component properties](rest_cli_component_getproperties_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

