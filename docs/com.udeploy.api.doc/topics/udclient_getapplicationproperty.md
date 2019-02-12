# getApplicationProperty

Get the value of a custom property on a application

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplicationProperty [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|name|string|true|Name of the property|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplicationProperty
  -application JPetStore
  -name Prop1
```

Related REST command: [Get the value of a custom property on a application](rest_cli_application_getproperty_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

