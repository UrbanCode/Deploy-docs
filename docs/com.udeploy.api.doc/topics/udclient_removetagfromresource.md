# removeTagFromResource

Remove a tag from a resource

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  removeTagFromResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|tag|string|true|Name of the tag|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  removeTagFromResource
  -resource /Resource1/Subresource1
  -tag Tag1
```

Related REST command: [Remove a tag from a resource](rest_cli_resource_tag_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

