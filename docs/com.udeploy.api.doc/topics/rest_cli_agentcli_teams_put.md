# Add an agent to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Application".|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/teams?
  ?agent=myAgent&team=MyTeam" -X PUT
```

Related CLI command: [addAgentToTeam](udclient_addagenttoteam.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

