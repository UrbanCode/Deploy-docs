# List base resources

This command lists the base resources on the connected IBM UrbanCode Deploy server.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/baseResources
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/baseResources
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "name": "Top-level container",
    "id": "330eeab2-d3b7-41fc-b1c2-83842b3a99df"
  },
  {
    "name": "Other top-level container",
    "id": "a6e8bcbd-0be9-4854-a0a4-600c77b2fbe1"
  }
]
```

**Parent topic:** [rest/component resource](../../com.ibm.edt.api.doc/topics/rest_component.md)

