# Get information about a status

## Request

```
GET https://{hostname}:{port}
    /cli/status/getStatus?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|false|Type of status \(inventory, version, or snapshot\); this parameter is required you specify the name of the status instead of the ID|
|status|string|true|Name or ID of the status|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "061056cc-9433-4036-ac11-b3c0b84e7018",
    "type": "INVENTORY",
    "name": "Active",
    "active": true,
    "description": "Currently Deployed",
    "color": "#B3D66D",
    "unique": true
  }
]
```

Related CLI command: [getStatus](udclient_getstatus.md).

**Parent topic:** [status resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_status.md)

