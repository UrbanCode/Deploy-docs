# addEnvironmentProperty

Create a component environment property

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addEnvironmentProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|
|component|string|true|ID of the component|
|label|string|false|Label of the property|
|default|string|false|Default value|
|description|string|false|Description for the property|
|required|boolean|false|Whether the property is required|
|pattern|string|false|A regular expression that specifies valid values for the property|
|secure|boolean|false|Specify true to create a secure property|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addEnvironmentProperty 
  -name MyProperty 
  -component d2e59ca4-a2f5-4851-9c85-629c1019ba20 
  -required true
  
```

Related REST command: [Create a component environment property](rest_cli_component_addenvprop_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

