# getStatus

Get information about a status

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getStatus [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|false|Type of status \(inventory, version, or snapshot\); this parameter is required you specify the name of the status instead of the ID|
|status|string|true|Name or ID of the status|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getStatus
  -type inventory
  -status Active
```

## Example response

```
[
  {
    "id": "061056cc-9433-4036-ac11-b3c0b84e7018",
    "type": "INVENTORY",
    "name": "Active",
    "active": true,
    "description": "Currently Deployed",
    "color": "#B3D66D",
    "unique": true
  }
]
```

Related REST command: [Get information about a status](rest_cli_status_getstatus_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

