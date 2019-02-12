# Return all tags on a component

## Request

```
GET https://{hostname}:{port}
    /cli/component/tag?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "13a1604a-ecea-4f07-b85e-6b395ade161a",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Component"
  },
  {
    "id": "d140ae5a-dfb0-477a-910b-762cc0d99cc6",
    "name": "Tag2",
    "color": "#7fff00",
    "description": "",
    "objectType": "Component"
  }
]
```

Related CLI command: [getTagsOnComponent](udclient_gettagsoncomponent.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

