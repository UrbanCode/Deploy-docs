# getAgentPool

Get information about an agent pool

Returns a JSON representation of an agent pool.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAgentPool [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|pool|string|true|Name or ID of the agent pool|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getAgentPool 
  -pool Pool1
```

## Example response

```
{
  "id": "8bfa2e62-2376-466c-91c5-3f79b3e6f655",
  "name": "Pool1",
  "active": true,
  "description": "",
  "status": "ONLINE",
  "security": {
    "read": true,
    "write": true
  },
  "agentIds": "897fa851-fab1-455f-bd84-fe83ae43c441,bdc2019c-78ae-403c-a528-22b31ae3c183",
  "extendedSecurity": {
    "read": true,
    "write": true,
    "Create Agent Pools": true,
    "Edit Agent Pools": true,
    "View Agent Pools": true,
    "teams": [
      {
        "teamId": "ea307e2e-d6be-4092-a7e8-e8e02274de7e",
        "teamLabel": "My team"
      }
    ]
  }
}
```

Related REST command: [Get information about an agent pool](rest_cli_agentpool_info_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

