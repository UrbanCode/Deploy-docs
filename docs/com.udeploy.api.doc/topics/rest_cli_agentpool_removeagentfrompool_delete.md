# Remove an agent from an agent pool

## Request

```
DELETE https://{hostname}:{port}
    /cli/agentPool/removeAgentFromPool?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|pool|string|true|Name or ID of the agent pool|
|agent|string|true|Name or ID of the agent|

Related CLI command: [removeAgentFromPool](udclient_removeagentfrompool.md).

**Parent topic:** [agentPool resource](../../com.udeploy.api.doc/topics/rest_cli_agentpool.md)

