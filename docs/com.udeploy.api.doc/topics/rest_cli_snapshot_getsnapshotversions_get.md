# Get the list of versions in a snapshot

## Request

```
GET https://{hostname}:{port}
    /cli/snapshot/getSnapshotVersions?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/snapshot/getSnapshotVersions
  ?application=JPetStore&snapshot=mySnapshot"
```

Related CLI command: [getSnapshotVersions](udclient_getsnapshotversions.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

