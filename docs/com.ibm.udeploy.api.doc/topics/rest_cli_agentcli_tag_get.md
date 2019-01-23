# List all tags on an agent

## Request

```
GET https://{hostname}:{port}
    /cli/agentCLI/tag?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "34afc9d1-e6d7-420f-a40c-30e6d3bf0c34",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Agent"
  },
  {
    "id": "74c02e58-e532-47d7-ba98-66d1ac20c361",
    "name": "Tag2",
    "color": "#7fff00",
    "description": "",
    "objectType": "Agent"
  }
]
```

Related CLI command: [getTagsOnAgent](udclient_gettagsonagent.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

