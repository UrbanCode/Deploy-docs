# Add component to an application

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{componentId}/componentToApplication/{applicationId}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationId|string|true|The ID of the application|
|componentId|string|true|The ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/
  component/4da842b6-f144-44d0-aa0d-4b02a7b1a1f6/
  componentToApplication/995b585e-af00-494e-a655-fa47d4b0dbee
  -H "Accept: application/json"
```

## Example response

```
{
  "componentId": "4da842b6-f144-44d0-aa0d-4b02a7b1a1f6",
  "applicationId": "995b585e-af00-494e-a655-fa47d4b0dbee"
}
```

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

