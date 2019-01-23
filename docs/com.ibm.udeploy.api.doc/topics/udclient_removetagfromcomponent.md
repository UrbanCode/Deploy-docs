# removeTagFromComponent

Delete a tag from a component

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  removeTagFromComponent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|tag|string|true|Name of the tag|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeTagFromComponent
  -component JPetStore-APP
  -tag Tag1
```

Related REST command: [Delete a tag from a component](rest_cli_component_tag_delete.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

