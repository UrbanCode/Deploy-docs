# List the components for an application

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{applicationName}/applicationComponents
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationName|string|true|The name of application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/
  995b585e-af00-494e-a655-fa47d4b0dbee/applicationComponents
  -H "Accept: application/json"
```

## Example response

```
{
  "components": [
    {
      "name": "Component A",
      "id": "bc2e1fc2-f8a3-4fa6-af7d-21bcc2ea9d67"
    },
    {
      "name": "Component B",
      "id": "9c8d02a4-a021-4afd-86c4-1ef8dace4325"
    },
    {
      "name": "Component C",
      "id": "4da842b6-f144-44d0-aa0d-4b02a7b1a1f6"
    }
  ]
}
```

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

