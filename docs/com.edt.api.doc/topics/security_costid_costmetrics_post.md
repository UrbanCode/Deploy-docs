# Create cost metrics for a given cost center cost center

This command creates cost metrics for a cost center from the supplied JSON string.

## Request

```
POST http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}/costmetrics
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|costCenterId|string|true|ID of the cost center|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "costMetrics": [{
    "cost": "Cost",
    "costFactors": [{
      "costMetricId": "Cost metric ID",
      "costResource": [{
        "costCenterId": "Cost center ID",
        "id": "ID",
        "name": "Resource name",
        "properties": {"name": "value (Optional - repeat 
  as necessary"},
        "resourceId": "Resource ID",
        "resoutceType": "resource type"
      }],
      "costResourceId": "Cost Resource ID",
      "id": "ID",
      "type": "Type"
    }],
    "costMetricType": "Cost metric type",
    "id": "Mertics ID",
    "rate": "Cost rate"
  }],
  "id": "Cloud ID"
}

```

**Parent topic:** [security/costcenter resource](../../com.edt.api.doc/topics/security_costcenter_.md)

