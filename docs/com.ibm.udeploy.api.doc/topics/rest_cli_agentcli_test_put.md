# Test the connection from an agent to the server

The agent's JMS and HTTP connections to the server will be tested.

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/test?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/test
  ?agent=myAgent" -X PUT
```

Related CLI command: [testAgent](udclient_testagent.md).

**Parent topic:** [agentCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentcli.md)

