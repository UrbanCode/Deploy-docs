# Create an agent pool

## Request

```
PUT https://{hostname}:{port}
    /cli/agentPool/createAgentPool
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

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

Related CLI command: [createAgentPool](udclient_createagentpool.md).

**Parent topic:** [agentPool resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_agentpool.md)

