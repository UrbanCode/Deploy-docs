# getAgentPools

Get information about all agent pools

Return a JSON representation of all agent pools.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAgentPools [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|active|boolean|false|Specify true \(the default\) to include active agent pools|
|inactive|boolean|false|Specify true to include inactive agent pools; the default is false|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getAgentPools
```

## Example response

```
[
  {
    "id": "11dda768-525d-4055-a7d2-5fb0e86ad236",
    "name": "Pool1",
    "active": true,
    "description": "",
    "status": "ONLINE"
  },
  {
    "id": "8bfa2e62-2376-466c-91c5-3f79b3e6f655",
    "name": "Pool2",
    "active": true,
    "description": "",
    "status": "ONLINE"
  }
]
```

Related REST command: [Get information about all agent pools](rest_cli_agentpool_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

