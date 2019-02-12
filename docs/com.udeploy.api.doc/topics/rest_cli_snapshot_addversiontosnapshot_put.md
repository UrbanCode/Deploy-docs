# Add a component version to a snapshot

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/addVersionToSnapshot?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot|
|application|string|false|Name of the application; this value is required if you specify the snapshot name instead of ID|
|version|string|true|Name or ID of the component version|
|component|string|false|Name of the component; this value is required if you specify the component name instead of ID|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/snapshot/addVersionToSnapshot
  ?application=MyApplication&component=MyComponent&snapshot=MySnapshot&version=1.2"
  -X PUT
```

Related CLI command: [addVersionToSnapshot](udclient_addversiontosnapshot.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

