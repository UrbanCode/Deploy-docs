# removeEnvironmentProperty

Delete a component environment property

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeEnvironmentProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property to remove|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeEnvironmentProperty 
  -name MyProperty 
  -component d2e59ca4-a2f5-4851-9c85-629c1019ba20
  
```

Related REST command: [Delete a component environment property](rest_cli_component_removeenvprop_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

