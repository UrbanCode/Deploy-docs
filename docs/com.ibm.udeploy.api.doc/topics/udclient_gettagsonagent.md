# getTagsOnAgent

List all tags on an agent

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getTagsOnAgent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|agent|string|true|Name or ID of the agent|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getTagsOnAgent
  -agent Agent1
```

## Example response

```
[
  {
    "id": "34afc9d1-e6d7-420f-a40c-30e6d3bf0c34",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Agent"
  },
  {
    "id": "74c02e58-e532-47d7-ba98-66d1ac20c361",
    "name": "Tag2",
    "color": "#7fff00",
    "description": "",
    "objectType": "Agent"
  }
]
```

Related REST command: [List all tags on an agent](rest_cli_agentcli_tag_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

