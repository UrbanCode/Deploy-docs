# Get information about a cost center

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/{costCenterId}
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
  http://myserver.example.com:8080/landscaper/security/costcenter/adbfe6b3-36d6-4689-964a-0e1d7db7fa01
  -H "Accept: application/json"
```

## Example response

```
{
  "id": "adbfe6b3-36d6-4689-964a-0e1d7db7fa01",
  "name": "My OpenStack Cloud",
  "source": "CLOUD"
}
```

**Parent topic:** [security/costcenter resource](../../com.edt.api.doc/topics/security_costcenter_.md)

