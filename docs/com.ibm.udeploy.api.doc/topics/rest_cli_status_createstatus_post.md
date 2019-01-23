# Create a status

## Request

```
POST https://{hostname}:{port}
    /cli/status/createStatus?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|true|Type of status \(inventory, version, or snapshot\)|
|status|string|true|Name of the new status|
|color|string|false|Color of the new status \(HTML color strings or valid color names\) \(Optional\)|
|description|string|false|Description of the new status \(Optional\)|
|unique|string|false|Specify true to make this status unique \(Optional\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "abff7bb6-bf95-417e-bf00-b0a8678e832a",
  "type": "VERSION",
  "name": "Documented",
  "active": true,
  "color": "#0077FF",
  "unique": false
}
```

Related CLI command: [createStatus](udclient_createstatus.md).

**Parent topic:** [status resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_status.md)

