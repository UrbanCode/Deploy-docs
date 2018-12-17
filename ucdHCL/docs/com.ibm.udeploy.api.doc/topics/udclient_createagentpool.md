# createAgentPool

Create an agent pool

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createAgentPool [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agents": [
    "Agent ID or name",
    "Agent ID or name (repeat as necessary)"
  ],
  "description": "Description",
  "name": "Name of the agent pool"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createAgentPool newPool.json
```

## Example JSON request

```
{
  "name": "New pool",
  "description": "My new agent pool",
  "agents": [
    "Agent1",
    "Agent2"
  ]
}
```

## Example response

```
{
  "id": "62eb25dd-edc0-4900-a4c7-25b440abb1a3",
  "name": "New pool",
  "active": true,
  "description": "My new agent pool",
  "status": "ONLINE"
}
```

Related REST command: [Create an agent pool](rest_cli_agentpool_createagentpool_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

