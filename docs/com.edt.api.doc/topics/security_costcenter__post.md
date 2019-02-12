# Create a cost center

This command creates a cost center from the supplied JSON string.

## Request

```
POST http://{hostname}:{port}
  /landscaper/security/costcenter/
Accept: application/json
Content-Type: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "name": "Cost center name",
  "source": "Cost center source, such as CLOUD or UCD"
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper
  /security/costcenter/" 
  -H "Accept: application/json" 
  -H "Content-Type: application/json" 
  -X POST 
  -d '{"name":"MyNewCostCenter","source":"CLOUD"}'
```

## Example response

```
{
  "id": "7adb3aa0-fab4-4ba8-ab0a-b71afa49d286",
  "name": "MyNewCostCenter",
  "source": "CLOUD"
}

```

**Parent topic:** [security/costcenter resource](../../com.edt.api.doc/topics/security_costcenter_.md)

