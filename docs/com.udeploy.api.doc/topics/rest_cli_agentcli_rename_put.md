# Rename an agent

Rename an agent. Use this command if running the agent configuration script in the agent bin directory is not convenient. Only the administrator can run this method.

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/rename?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent to rename|
|name|string|true|The new name for the agent|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/agentCLI/rename?
  agent=MyAgent&name=NewAgentName" -X PUT
```

Related CLI command: [forceRenameAgent](udclient_forcerenameagent.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

