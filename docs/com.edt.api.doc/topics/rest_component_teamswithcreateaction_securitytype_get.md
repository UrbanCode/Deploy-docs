# List teams that can be associated with an environment

This command lists the teams on the connected IBM UrbanCode Deploy server that can be associated with a newly provisioned environment.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/teamsWithCreateAction/{securityType}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|securityType|string|true|The type of element for which to get possible teams, such as Application, Component, or Environment.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

