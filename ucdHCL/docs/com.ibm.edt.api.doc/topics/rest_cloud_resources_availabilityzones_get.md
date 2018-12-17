# List the availability zones on a cloud

This command returns a list of the availability zones on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/availabilityZones
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/availabilityZones
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "state": "available",
    "id": "us-east-1a",
    "region_name": "us-east-1",
    "name": "us-east-1a"
  },
  {
    "state": "available",
    "id": "us-east-1b",
    "region_name": "us-east-1",
    "name": "us-east-1b"
  },
  {
    "state": "available",
    "id": "us-east-1d",
    "region_name": "us-east-1",
    "name": "us-east-1d"
  },
  {
    "state": "available",
    "id": "us-east-1e",
    "region_name": "us-east-1",
    "name": "us-east-1e"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

