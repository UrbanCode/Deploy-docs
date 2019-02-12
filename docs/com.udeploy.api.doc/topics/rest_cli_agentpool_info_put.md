# Get information about an agent pool

Returns a JSON representation of an agent pool.

## Request

```
PUT https://{hostname}:{port}
    /cli/agentPool/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|pool|string|true|Name or ID of the agent pool|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "8bfa2e62-2376-466c-91c5-3f79b3e6f655",
  "name": "Pool1",
  "active": true,
  "description": "",
  "status": "ONLINE",
  "security": {
    "read": true,
    "write": true
  },
  "agentIds": "897fa851-fab1-455f-bd84-fe83ae43c441,bdc2019c-78ae-403c-a528-22b31ae3c183",
  "extendedSecurity": {
    "read": true,
    "write": true,
    "Create Agent Pools": true,
    "Edit Agent Pools": true,
    "View Agent Pools": true,
    "teams": [
      {
        "teamId": "ea307e2e-d6be-4092-a7e8-e8e02274de7e",
        "teamLabel": "My team"
      }
    ]
  }
}
```

Related CLI command: [getAgentPool](udclient_getagentpool.md).

**Parent topic:** [agentPool resource](../../com.udeploy.api.doc/topics/rest_cli_agentpool.md)

