# Add a status to a snapshot

## Request

```
PUT https://{hostname}:{port}
    /cli/snapshot/addStatusToSnapshot?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot.|
|application|string|false|Name or ID of the application; this value is required if you specify the snapshot name instead of the ID.|
|statusName|string|true|Name or ID of the status. This value cannot be longer than 36 characters.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  snapshot/addStatusToSnapshot?application=MyApplication&snapshot=MySnapshot
  statusName=NewStatus" 
  -X PUT

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

Related CLI command: [addStatusToSnapshot](udclient_addstatustosnapshot.md).

**Parent topic:** [snapshot resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_snapshot.md)

