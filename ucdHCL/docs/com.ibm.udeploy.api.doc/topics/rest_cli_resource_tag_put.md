# Add a tag to a resource

## Request

```
PUT https://{hostname}:{port}
    /cli/resource/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

Related CLI command: [addTagToResource](udclient_addtagtoresource.md).

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

