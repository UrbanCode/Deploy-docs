# getTagsOnComponent

Return all tags on a component

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getTagsOnComponent [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getTagsOnComponent
  -component JPetStore-APP
```

## Example response

```
[
  {
    "id": "13a1604a-ecea-4f07-b85e-6b395ade161a",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Component"
  },
  {
    "id": "d140ae5a-dfb0-477a-910b-762cc0d99cc6",
    "name": "Tag2",
    "color": "#7fff00",
    "description": "",
    "objectType": "Component"
  }
]
```

Related REST command: [Return all tags on a component](rest_cli_component_tag_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

