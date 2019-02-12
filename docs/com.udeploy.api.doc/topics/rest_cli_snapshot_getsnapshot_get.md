# Get information about a snapshot

## Request

```
GET https://{hostname}:{port}
    /cli/snapshot/getSnapshot?{parameters}
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
   
  "https://myserver.example.com:8443/cli/snapshot/getSnapshot
  ?application=JPetStore&snapshot=mySnapshot
```

## Example response

```
{
  "application": {
    "security": {
      "read": true,
      "Create Applications": true,
      "Delete": true,
      "Edit Basic Settings": true,
      "Manage Blueprints": true,
      "Manage Components": true,
      "Manage Environments": true,
      "Manage Processes": true,
      "Manage Properties": true,
      "Manage Snapshots": true,
      "Manage Teams": true,
      "Run Component Processes": true,
      "View Applications": true
    },
    "componentCount": 16,
    "extendedSecurity": {
      "read": true,
      "Create Applications": true,
      "Delete": true,
      "Edit Basic Settings": true,
      "Manage Blueprints": true,
      "Manage Components": true,
      "Manage Environments": true,
      "Manage Processes": true,
      "Manage Properties": true,
      "Manage Snapshots": true,
      "Manage Teams": true,
      "Run Component Processes": true,
      "View Applications": true,
      "teams": [{
        "teamId": "86739325-1ebb-4fb9-8a0f-a73c1e4d88c8",
        "teamLabel": "Landscaper",
        "resourceTypeId": "20000000000000000000000000000100",
        "resourceTypeName": "Application"
      }]
    },
    "propSheet": {
      "id": "ad6279a0-f140-4398-a238-cedb26880e2c",
      "path": "applications\/413b1470-3dae-446c-95fa-77873a5daaa9\/propSheet",
      "version": 1,
      "versionCount": 1,
      "commit": 10231,
      "versioned": true
    },
    "id": "413b1470-3dae-446c-95fa-77873a5daaa9",
    "securityResourceId": "ba1e7e3e-8642-45f9-a378-7528a82deb9a",
    "name": "JPetStore",
    "description": "",
    "created": 1389979285087,
    "enforceCompleteSnapshots": false,
    "active": true,
    "tags": [],
    "user": "Michael (mdelder@us.ibm.com)"
  },
  "id": "8724200d-9cd1-4b31-90e2-9ab8b0edb55d",
  "name": "MySnapshot",
  "description": "",
  "created": 1410462609512,
  "active": true,
  "versionsLocked": false,
  "configLocked": false,
  "applicationId": "413b1470-3dae-446c-95fa-77873a5daaa9",
  "user": "jsmith"
}
```

Related CLI command: [getSnapshot](udclient_getsnapshot.md).

**Parent topic:** [snapshot resource](../../com.udeploy.api.doc/topics/rest_cli_snapshot.md)

