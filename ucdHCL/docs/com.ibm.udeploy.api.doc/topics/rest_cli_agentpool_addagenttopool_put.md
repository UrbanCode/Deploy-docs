# Add an agent to an agent pool

## Request

```
PUT https://{hostname}:{port}
    /cli/agentPool/addAgentToPool?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|pool|string|true|Name or ID of the agent pool|
|agent|string|true|Name or ID of the agent|

Related CLI command: [addAgentToPool](udclient_addagenttopool.md).

**Parent topic:** [agentPool resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentpool.md)

