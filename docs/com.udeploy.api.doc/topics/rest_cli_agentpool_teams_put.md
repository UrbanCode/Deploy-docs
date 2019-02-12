# Add an agent pool to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/agentPool/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agentPool|string|true|Name or ID of the agent pool|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard agent pool".|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentPool/teams?
  ?agentPool=myAgentPool&team=MyTeam" -X PUT
```

Related CLI command: [addAgentPoolToTeam](udclient_addagentpooltoteam.md).

**Parent topic:** [agentPool resource](../../com.udeploy.api.doc/topics/rest_cli_agentpool.md)

