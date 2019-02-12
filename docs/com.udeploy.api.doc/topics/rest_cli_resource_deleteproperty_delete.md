# Delete a resource property

## Request

```
DELETE https://{hostname}:{port}
    /cli/resource/deleteProperty?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|name|string|true|Name of the property|

Related CLI command: [deleteResourceProperty](udclient_deleteresourceproperty.md).

**Parent topic:** [resource resource](../../com.udeploy.api.doc/topics/rest_cli_resource.md)

