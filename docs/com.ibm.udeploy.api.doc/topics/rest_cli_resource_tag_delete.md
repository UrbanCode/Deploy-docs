# Remove a tag from a resource

## Request

```
DELETE https://{hostname}:{port}
    /cli/resource/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|tag|string|true|Name of the tag|

Related CLI command: [removeTagFromResource](udclient_removetagfromresource.md).

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

