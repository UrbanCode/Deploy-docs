# Upgrade an agent

The agent will be upgraded to the agent version corresponding with the UrbanCode Deploy server version.

## Request

```
PUT https://{hostname}:{port}
    /cli/agentCLI/upgrade?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [upgradeAgent](udclient_upgradeagent.md).

**Parent topic:** [agentCLI resource](../../com.udeploy.api.doc/topics/rest_cli_agentcli.md)

