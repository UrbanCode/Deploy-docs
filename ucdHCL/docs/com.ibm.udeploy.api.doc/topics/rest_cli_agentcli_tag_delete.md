# Delete a tag from an agent

## Request

```
DELETE https://{hostname}:{port}
    /cli/agentCLI/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|tag|string|true|Name of the tag|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/tag
  ?agent=myAgent&tag=mytag" -X DELETE
```

Related CLI command: [removeTagFromAgent](udclient_removetagfromagent.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

