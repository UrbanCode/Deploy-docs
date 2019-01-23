# Returns a JSONObject with count of agents to status. Expected format: \{ "ONLINE":4, "UPGRADE\_RECOMMENDED":1 \} Requires Settings Tab permission

## Request

```
GET https://{hostname}:{port}
    /cli/agentCLI/statuses
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getAgentStatuses](udclient_getagentstatuses.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

