# upgradeAgent

Upgrade an agent

The agent will be upgraded to the agent version corresponding with the UrbanCode Deploy server version.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  upgradeAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  upgradeAgent
  -agent Agent1
```

Related REST command: [Upgrade an agent](rest_cli_agentcli_upgrade_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

