# List the regions

This command returns a list of regions on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/regions
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/regions
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

