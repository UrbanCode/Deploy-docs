# addTagToAgent

Add a tag to an agent

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addTagToAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addTagToAgent
  -agent Agent1
  -tag Tag1
```

Related REST command: [Add a tag to an agent](rest_cli_agentcli_tag_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

