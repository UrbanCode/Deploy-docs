# List all component resources

This command returns a list of components.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/resources?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|page|int|false| |
|application|string|false| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/
  component/resources
  -H "Accept: application/json"
```

## Example response

```
[
{
  "name": "Component A",
  "id": "baec4682-842e-46e6-a84d-db67d87778a0",
  "category": "component",
  "subcategory": "ucd",
  "url": "http://myserver.example.com:9080",
  "icon": "images/editor/Component.gif"
},
{
  "name": "Component B",
  "id": "f302cdf3-0877-440c-84b8-40e2995131ed",
  "category": "component",
  "subcategory": "ucd",
  "url": "http://myserver.example.com:9080",
  "icon": "images/editor/Component.gif"
},
{
  "name": "Component C",
  "id": "2ef1016a-b0f3-44e6-8091-078d91a1bb87",
  "category": "component",
  "subcategory": "ucd",
  "url": "http://myserver.example.com:9080",
  "icon": "images/editor/Component.gif"
}
]

```

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

