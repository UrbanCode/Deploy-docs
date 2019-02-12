# getTagsOnResource

List the tags on a resource

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getTagsOnResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getTagsOnResource
  -resource /Resource1/Subresource1
```

## Example response

```
[
  {
    "id": "eeff1b7d-ef7c-4052-812b-a97405b97606",
    "name": "Tag1",
    "color": "#FFFFFF",
    "description": "",
    "objectType": "Resource"
  },
  {
    "id": "b03313f2-a3fa-4ac8-a84a-32869958ba06",
    "name": "Tag2",
    "color": "#87ceeb",
    "description": "",
    "objectType": "Resource"
  }
]
```

Related REST command: [List the tags on a resource](rest_cli_resource_tag_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

