# Get a resource property

## Request

```
GET https://{hostname}:{port}
    /cli/resource/getProperty?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|name|string|true|Name of the property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

Related CLI command: [getResourceProperty](udclient_getresourceproperty.md).

**Parent topic:** [resource resource](../../com.udeploy.api.doc/topics/rest_cli_resource.md)

