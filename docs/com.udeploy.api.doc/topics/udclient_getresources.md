# getResources

List resources

This command returns a JSONArray representation of all top-level resources, or all children of a specified parent resource.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getResources [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|parent|string|false|Specify the path to a parent resource to show children of that resource, such as /AllAgents/MyAgentGroup. Leave this field blank to show all top-level resources. \(Optional\)|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getResources
  -parent "/JPetStore agents"
```

## Example response

```
[
  {
    "id": "5fcc9f43-63eb-40bc-bcd6-3c0b2c124dce",
    "securityResourceId": "67bd54e9-39c5-4f49-b4d6-cf6eee286589",
    "name": "agent1",
    "path": "\/JPetStore agents\/agent1",
    "active": true,
    "description": "",
    "inheritTeam": true,
    "impersonationPassword": "****",
    "impersonationUseSudo": false,
    "impersonationForce": false,
    "type": "agent",
    "status": "ONLINE",
    "hasAgent": true,
    "tags": []
  },
  {
    "id": "1fd3d080-df81-4cd2-aa6d-58ae551fc3213",
    "securityResourceId": "38a18720-abef-4931-9ac0-62d19c06e506",
    "name": "agent2",
    "path": "\/JPetStore agents\/agent2",
    "active": true,
    "description": "",
    "inheritTeam": true,
    "impersonationPassword": "****",
    "impersonationUseSudo": false,
    "impersonationForce": false,
    "type": "agent",
    "status": "OFFLINE",
    "hasAgent": true,
    "tags": []
  }
]
```

Related REST command: [List resources](rest_cli_resource_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

