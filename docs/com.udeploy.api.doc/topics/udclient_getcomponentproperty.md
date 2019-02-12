# getComponentProperty

Get the value of a custom property on a component

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentProperty
  -component JPetStore-APP
  -name Prop1
```

Related REST command: [Get the value of a custom property on a component](rest_cli_component_getproperty_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

