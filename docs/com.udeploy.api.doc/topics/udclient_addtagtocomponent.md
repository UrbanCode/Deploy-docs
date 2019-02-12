# addTagToComponent

Add a tag to a component

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addTagToComponent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addTagToComponent
  -component JPetStore-APP
  -tag Tag1
```

Related REST command: [Add a tag to a component](rest_cli_component_tag_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

