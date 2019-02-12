# getTagsOnApplication

List all tags on an application

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getTagsOnApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getTagsOnApplication
  -application JPetStore
```

## Example response

```
[
  {
    "id": "f3c52993-ffe4-464a-b34c-0abc1df7f995",
    "name": "Tag1",
    "color": "#dda0dd",
    "description": "",
    "objectType": "Application"
  },
  {
    "id": "ae47b2dc-8153-42c9-8094-207703a439e4",
    "name": "Tag2",
    "color": "#ffff00",
    "description": "",
    "objectType": "Application"
  }
]
```

Related REST command: [List all tags on an application](rest_cli_application_tag_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

