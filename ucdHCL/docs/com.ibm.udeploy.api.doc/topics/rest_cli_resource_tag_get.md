# List the tags on a resource

## Request

```
GET https://{hostname}:{port}
    /cli/resource/tag?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "eeff1b7d-ef7c-4052-812b-a97405b97606",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Resource"
  },
  {
    "id": "b03313f2-a3fa-4ac8-a84a-32869958ba06",
    "name": "Tag2",
    "color": "#87ceeb",
    "description": "",
    "objectType": "Resource"
  }
]
```

Related CLI command: [getTagsOnResource](udclient_gettagsonresource.md).

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

