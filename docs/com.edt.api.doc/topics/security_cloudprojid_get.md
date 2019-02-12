# Get information about a cloud project

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudproject/{cloudProjectId}
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
  http://myserver.example.com:8080/landscaper/security/cloudproject/1241aa10-5f98-4f11-be63-b21ad69c3e4b
```

## Example response

```
{
    "cloudProviderId": "fe8b00b5-0b1b-473a-b355-2312394cd12b7",
    "dateCreated": 1406666213336,
    "description": "",
    "displayName": "JSmith@My OpenStack server",
    "id": "1241aa10-5f98-4f11-be63-b21ad69c3e4b",
    "name": "JSmith",
    "properties": [],
    "readOnly": true,
    "type": "AUTH_REALM"
}
```

**Parent topic:** [security/cloudproject resource](../../com.edt.api.doc/topics/security_cloudproject_.md)

