# Get cost metrics for instances

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}/costmetrics/costmetricType/{costMetricType}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|costCenterId|string|true|ID of the cost center|
|costMetricType|string|true|Cost metric type, such as INSTANCE, VOLUME, COMPONENT, or FLOATINGIP|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
   
  -H 'Accept: application/json'
  http://myserver.example.com:8080/landscaper/security/
  costcenter/0bce5aec-e4f4-4e51-a52c-dfe0a52aca96/
  costmetrics/costmetricType/FLOATINGIP
```

## Example response

```
[
  {
    "id": "5cbca38c-2b9c-4d56-9f78-a71c28b53a9f",
    "costMetricType": "FLOATINGIP",
    "cost": 1.5,
    "rate": "PER_HOUR",
    "costFactors": []
  }
]
```

**Parent topic:** [security/costcenter resource](../../com.ibm.edt.api.doc/topics/security_costcenter_.md)

