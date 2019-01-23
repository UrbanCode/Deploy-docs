# Get information about all agent pools

Return a JSON representation of all agent pools.

## Request

```
GET https://{hostname}:{port}
    /cli/agentPool?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|active|boolean|false|Specify true \(the default\) to include active agent pools|
|inactive|boolean|false|Specify true to include inactive agent pools; the default is false|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "11dda768-525d-4055-a7d2-5fb0e86ad236",
    "name": "Pool1",
    "active": true,
    "description": "",
    "status": "ONLINE"
  },
  {
    "id": "8bfa2e62-2376-466c-91c5-3f79b3e6f655",
    "name": "Pool2",
    "active": true,
    "description": "",
    "status": "ONLINE"
  }
]
```

Related CLI command: [getAgentPools](udclient_getagentpools.md).

**Parent topic:** [agentPool resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentpool.md)

