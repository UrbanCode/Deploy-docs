# List the regions for a cloud type

This command lists the regions on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/regions/blueprint/{blueprint}/configuration/{configuration}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|The blueprint ID|
|configuration|string|true|The configuration file ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/regions/
  blueprint/MyBlueprint/configuration/MyConfig
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "id": "us-east-1",
    "name": "US East (Northern Virginia)"
  },
  {
    "id": "ap-northeast-1",
    "name": "Asia Pacific (Tokyo)"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

