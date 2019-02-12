# deleteResource

Delete a resource

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

## Example

```
udclient  -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteResource
  -resource "/ResourceGroup/My resource"
```

**Note:** When you specify the name of the resource, type the complete path to the resource, including the initial '/' character if the resource is not in any higher-level group.

Related REST command: [Delete a resource](rest_cli_resource_deleteresource_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

