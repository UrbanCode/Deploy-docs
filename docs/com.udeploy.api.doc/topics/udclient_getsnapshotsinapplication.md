# getSnapshotsInApplication

Get information about snapshots in an application

Snapshots are listed from most recent to least recent.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getSnapshotsInApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|maxResults|int|false|Cap the number of results. Any value less than 1 returns all results.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getSnapshotsInApplication 
  -application MyApplication

```

## Example JSON request

```
[
  {
    "id": "305749d0-9838-4fce-a8bd-7d25b4ffd5f7",
    "name": "Snapshot1",
    "created": 1441386527766,
    "active": true,
    "versionsLocked": false,
    "configLocked": false,
    "applicationId": "2d741420-fd31-443d-95eb-472d334f8ec9",
    "user": "jsmith"
  },
  {
    "id": "5ab250dd-37f8-4a6e-9ec1-8cf0b547eb25",
    "name": "Snapshot2",
    "created": 1441386081196,
    "active": true,
    "versionsLocked": false,
    "configLocked": false,
    "applicationId": "2d741420-fd31-443d-95eb-472d334f8ec9",
    "user": "jsmith"
  }
]
```

Related REST command: [Get information about snapshots in an application](rest_cli_application_snapshotsinapplication_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

