# List statuses

This command lists all the statuses that are associated with a specified status type.

## Request

```
GET https://{hostname}:{port}
    /cli/status/getStatuses?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|true|Status type \(inventory, version, or snapshot\)|

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

Related CLI command: [getStatuses](udclient_getstatuses.md).

**Parent topic:** [status resource](../../com.udeploy.api.doc/topics/rest_cli_status.md)

