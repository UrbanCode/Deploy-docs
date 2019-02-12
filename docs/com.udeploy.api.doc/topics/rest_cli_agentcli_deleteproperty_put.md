# Remove a property from an agent

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/deleteProperty?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|name|string|true|Name of the property|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/deleteProperty
  ?agent=myAgent&name=newProperty" -X PUT
```

Related CLI command: [deleteAgentProperty](udclient_deleteagentproperty.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

