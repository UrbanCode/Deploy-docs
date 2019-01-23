# Update a cost center

This command updates a cost center from the supplied JSON string

## Request

```
PUT http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}
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
  "existingId": "Existing ID",
  "name": "Cost center name",
  "source": "Cost center source"
}

```

**Parent topic:** [security/costcenter resource](../../com.ibm.edt.api.doc/topics/security_costcenter_.md)

