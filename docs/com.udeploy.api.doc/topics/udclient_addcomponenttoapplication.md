# addComponentToApplication

Add a component to an application.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addComponentToApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name of the component|
|application|string|true|Name of the application|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addComponentToApplication
  -application JPetStore
  -component JPetStore-WEB
```

Related REST command: [Add a component to an application.](rest_cli_application_addcomponenttoapp_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

