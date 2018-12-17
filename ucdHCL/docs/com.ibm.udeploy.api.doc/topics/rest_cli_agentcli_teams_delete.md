# Remove an agent from a team

## Request

```
DELETE https://{hostname}:{port}
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
  ?agent=myAgent&team=MyTeam" -X DELETE
```

Related CLI command: [removeAgentFromTeam](udclient_removeagentfromteam.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

