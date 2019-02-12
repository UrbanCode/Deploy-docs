# getSystemProperty

Get the value of a system property

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getSystemProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getSystemProperty
  -name property1
```

## Example response

```
value001
```

Related REST command: [Get the value of a system property](rest_cli_systemconfiguration_getproperty_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

