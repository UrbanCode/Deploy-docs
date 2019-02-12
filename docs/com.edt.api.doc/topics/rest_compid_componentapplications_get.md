# List the applications and its components

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{componentId}/componentApplications
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|componentId|string|true|The ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/
  MyComponent/componentApplications
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "name": "MyApplication",
    "id": "a61039dc-bf63-43d4-9937-38dc358e2825",
    "components": [
      {
        "name": "MyComponent",
        "id": "515ab234-80a9-43ba-a782-27941024a4b3"
      },
      {
        "name": "OtherComponent",
        "id": "121ab234-1235-123d-a782-274234234456"
      }
    ]
  }
]
```

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

