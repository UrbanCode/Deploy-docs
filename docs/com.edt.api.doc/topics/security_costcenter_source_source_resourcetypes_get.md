# Get resource types for a given source

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/source/{source}/resourceTypes
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|source|string|true|source|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/costcenter/
  source/CLOUD/resourceTypes
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "id": "FLAVOR",
    "name": "FLAVOR",
    "displayName": "Flavor"
  },
  {
    "id": "INSTANCE_TYPE",
    "name": "INSTANCE_TYPE",
    "displayName": "Instance Type"
  },
  {
    "id": "REGION",
    "name": "REGION",
    "displayName": "Region"
  },
  {
    "id": "VOLUME",
    "name": "VOLUME",
    "displayName": "Volume"
  }
]
```

**Parent topic:** [security/costcenter resource](../../com.edt.api.doc/topics/security_costcenter_.md)

