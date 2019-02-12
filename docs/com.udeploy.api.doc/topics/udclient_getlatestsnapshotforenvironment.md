# getLatestSnapshotForEnvironment

Get the latest snapshot deployed to an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getLatestSnapshotForEnvironment [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|environment|string|true|Name or ID of the environment|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getLatestSnapshotForEnvironment
  -application MyApplication
  -environment MyEnvironment
```

## Example response

```
{
  "id": "2ef3189b-af8f-49f1-8476-a3d4ed440722",
  "name": "Snap5",
  "created": 1441388592826,
  "active": true,
  "versionsLocked": false,
  "configLocked": false,
  "applicationId": "2d741420-fd31-443d-95eb-472d334f8ec9",
  "user": "admin"
}

```

Related REST command: [Get the latest snapshot deployed to an environment](rest_cli_env_snapshot_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

