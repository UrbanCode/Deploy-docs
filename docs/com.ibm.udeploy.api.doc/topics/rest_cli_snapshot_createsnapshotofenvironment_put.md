# Take a snapshot of an environment

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/createSnapshotOfEnvironment?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|name|string|true|Name of the new snapshot|
|description|string|false|Snapshot description|
|excludeUnmapped|boolean|false|Exclude components with no resource in this environment \(default false\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "41eab076-deb6-4746-8b2d-9f491103a06c",
  "name": "NewSnapshot"
}
```

Related CLI command: [createSnapshotOfEnvironment](udclient_createsnapshotofenvironment.md).

**Parent topic:** [snapshot resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_snapshot.md)

