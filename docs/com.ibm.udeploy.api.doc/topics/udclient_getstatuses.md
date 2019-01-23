# getStatuses

List statuses

This command lists all the statuses that are associated with a specified status type.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getStatuses [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|true|Status type \(inventory, version, or snapshot\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getStatuses
  -type inventory
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

Related REST command: [List statuses](rest_cli_status_getstatuses_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

