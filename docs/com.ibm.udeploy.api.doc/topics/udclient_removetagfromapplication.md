# removeTagFromApplication

Remove a tag from an application

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeTagFromApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|tag|string|true|Name of the tag|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeTagFromApplication
  -application JPetStore
  -tag Tag1
```

Related REST command: [Remove a tag from an application](rest_cli_application_tag_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

