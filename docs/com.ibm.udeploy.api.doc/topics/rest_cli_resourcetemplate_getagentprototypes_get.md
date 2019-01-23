# Get all agent prototypes with this resource template as their ancestor

## Request

```
GET https://{hostname}:{port}
    /cli/resourceTemplate/getAgentPrototypes?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|template|string|true|Name or ID of resource template|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getAgentPrototypes](udclient_getagentprototypes.md).

**Parent topic:** [resourceTemplate resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resourcetemplate.md)

