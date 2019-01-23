# addStatusToSnapshot

Add a status to a snapshot

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addStatusToSnapshot [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot.|
|application|string|false|Name or ID of the application; this value is required if you specify the snapshot name instead of the ID.|
|statusName|string|true|Name or ID of the status. This value cannot be longer than 36 characters.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addStatusToSnapshot 
  -application MyApplication
  -snapshot MySnapshot 
  -statusName NewStatus
```

## Example response

```
{
  "id": "d3dfd0c8-90f5-427b-8432-3c71c086cc93",
  "name": "MySnapshot",
  "description": "",
  "created": 1450130946382,
  "active": true,
  "versionsLocked": false,
  "configLocked": false,
  "applicationId": "99822240-cc96-4e4e-91e9-bcc483521cec",
  "user": "jsmith"
}
```

Related REST command: [Add a status to a snapshot](rest_cli_snapshot_addstatustosnapshot_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

