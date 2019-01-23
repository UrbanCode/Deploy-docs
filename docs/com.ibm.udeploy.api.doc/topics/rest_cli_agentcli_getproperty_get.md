# Get the value of a property on an agent

## Request

```
GET https://{hostname}:{port}
    /cli/agentCLI/getProperty?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|
|name|string|true|Name of the property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/getProperty
  ?agent=myAgent&name=Hostname"
```

Related CLI command: [getAgentProperty](udclient_getagentproperty.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

