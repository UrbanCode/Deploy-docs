# Delete a snapshot

## Request

```
DELETE https://{hostname}:{port}
    /cli/snapshot/deleteSnapshot?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/snapshot/deleteSnapshot
  ?application=MyApplication&snapshot=Snapshot1" -X DELETE
```

Related CLI command: [deleteSnapshot](udclient_deletesnapshot.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

