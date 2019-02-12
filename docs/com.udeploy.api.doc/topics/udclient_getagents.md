# getAgents

Get information about all agents

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAgents [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|active|boolean|false|Specify true \(the default\) to include active agents.Specify false to hide active agents; this option is deprecated.|
|inactive|boolean|false|Deprecated. This parameter applies only to agents that were inactivated in versions prior to version 6.0. Agents in versions later than 6.0 can not be inactivated. Specify true to include these inactive agents; the default is false.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getAgents
```

## Example response

```
[
  {
    "id": "bdc2019c-78ae-403c-a528-22b31ae3c183",
    "name": "Agent1",
    "active": true,
    "licensed": false,
    "licenseType": "NONE",
    "status": "ONLINE",
    "version": "6.0.1.0.452394",
    "workingDirectory": "/opt/ibm-ucd/agent/var/work/",
    "impersonationPassword": "****",
    "impersonationForce": false,
    "tags": [
    ]
  }
]
```

Related REST command: [Get information about all agents](rest_cli_agentcli_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

