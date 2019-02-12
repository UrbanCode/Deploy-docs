# List the components for an application process

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{applicationName}/ProcessComponents?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationProcessName|string|false| |
|snapshotName|string|false| |
|returnName|string|false| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationName|string|true|The name of application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

