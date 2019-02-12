# Add a tag to an agent

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/tag?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|tag|string|true|Name of the tag|
|color|string|false|Hex representation of the color for the tag, such as FF0000. This parameter is used only if the tag is being created.|
|description|string|false|Description of the tag. This parameter is used only if the tag is being created.|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/tag
  ?agent=myAgent&tag=mytag" -X PUT
```

Related CLI command: [addTagToAgent](udclient_addtagtoagent.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

