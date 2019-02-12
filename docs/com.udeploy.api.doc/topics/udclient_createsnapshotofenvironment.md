# createSnapshotOfEnvironment

Take a snapshot of an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createSnapshotOfEnvironment [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|name|string|true|Name of the new snapshot|
|description|string|false|Snapshot description|
|excludeUnmapped|boolean|false|Exclude components with no resource in this environment \(default false\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createSnapshotOfEnvironment 
  -environment newEnvironment 
  -application JPetStore 
  -name NewSnapshot
```

## Example response

```
{
  "id": "41eab076-deb6-4746-8b2d-9f491103a06c",
  "name": "NewSnapshot"
}
```

Related REST command: [Take a snapshot of an environment](rest_cli_snapshot_createsnapshotofenvironment_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

