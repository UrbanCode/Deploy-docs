# Add component to a new application

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{componentId}/componentToNewApplication/{applicationName}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationName|string|true|The name of the application|
|componentId|string|true|The ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

