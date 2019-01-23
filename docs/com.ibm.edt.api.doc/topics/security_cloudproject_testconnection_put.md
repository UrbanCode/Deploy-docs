# Test connection to a cloud project

This command tests the connection to a cloud project

## Request

```
PUT http://{hostname}:{port}
  /landscaper/security/cloudproject/testConnection
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "cloudProviderId": "Cloud provider ID",
  "existingId": "Existing ID",
  "name": "Authorization user name",
  "properties": [{
    "name": "Property name",
    "value": "Property value"
  }]
}

```

## Example

```
curl -u jsmith:passwd 
   
  -H 'Content-Type: application/json'
  -d @testProject.json
  http://myserver.example.com:8080/landscaper/security/cloudproject/testConnection
  -X PUT
```

## Example JSON request

```
{
  "name": "admin",
  "cloudProviderId": "70789e1e-0b83-49da-98a3-34c4f949598a",
  "properties": [
    {
      "name": "functionalId",
      "value": "cloudUser"
    },
    {
      "name": "functionalPassword",
      "value": "myPasword123"
    }
  ]
}

```

## Example response

If the command is successful, the server returns a 200 code and no other information.

**Parent topic:** [security/cloudproject resource](../../com.ibm.edt.api.doc/topics/security_cloudproject_.md)

