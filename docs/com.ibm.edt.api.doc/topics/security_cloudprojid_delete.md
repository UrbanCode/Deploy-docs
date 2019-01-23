# Delete a cloud project

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/security/cloudproject/{cloudProjectId}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloudProjectId|string|true|ID of the cloud project|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudproject/1241aa10-5f98-4f11-be63-b21ad69c3e4b -X DELETE
```

**Parent topic:** [security/cloudproject resource](../../com.ibm.edt.api.doc/topics/security_cloudproject_.md)

