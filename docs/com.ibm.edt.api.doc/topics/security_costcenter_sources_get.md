# Get a list of cost center types

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/costcenter/sources
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/costcenter/sources
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "name": "CLOUD",
    "id": "CLOUD"
  },
  {
    "name": "UCD",
    "id": "UCD"
  }
]
```

**Parent topic:** [security/costcenter resource](../../com.ibm.edt.api.doc/topics/security_costcenter_.md)

