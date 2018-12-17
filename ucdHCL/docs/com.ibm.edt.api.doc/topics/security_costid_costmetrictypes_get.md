# Get cost metrics types for a cost metrics id

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}/costMetricTypes
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|costCenterId|string|true|ID of the cost center|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/costcenter/
  adbfe6b3-36d6-4689-964a-0e1d7db7fa01/costMetricTypes
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "id": "INSTANCE",
    "name": "INSTANCE",
    "displayName": "Instance"
  },
  {
    "id": "VOLUME",
    "name": "VOLUME",
    "displayName": "Volume"
  },
  {
    "id": "FLOATINGIP",
    "name": "FLOATINGIP",
    "displayName": "Floating IP"
  }
]
```

**Parent topic:** [security/costcenter resource](../../com.ibm.edt.api.doc/topics/security_costcenter_.md)

