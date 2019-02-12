# Restart an agent

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/restart?{parameters}
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
   
  "https://myserver.example.com:8443/cli/
  agentCLI/restart?agent=MyAgent" -X PUT
```

Related CLI command: [restartAgent](udclient_restartagent.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

