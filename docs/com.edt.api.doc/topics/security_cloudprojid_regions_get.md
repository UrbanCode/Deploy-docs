# List regions for a cloud project

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudproject/{cloudProjectId}/regions
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloudProjectId|string|true|ID of the cloud project|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
   
  -H 'Accept: application/json'
  http://myserver.example.com:8080/landscaper/security/
  cloudproject/f24a38bd-216f-4712-9a0a-cebdda06b033/regions
```

## Example response

```
[
  {
    "id": "us-east-1",
    "name": "US East (Northern Virginia)"
  },
  {
    "id": "us-west-1",
    "name": "US West (Northern California)"
  }
]
```

**Parent topic:** [security/cloudproject resource](../../com.edt.api.doc/topics/security_cloudproject_.md)

