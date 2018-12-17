# Create a cloud project

This command creates a cloud project from the supplied JSON string.

## Request

```
POST http://{hostname}:{port}
  /landscaper/security/cloudproject/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "cloudProviderId": "The cloud provider ID for this cloud 
  project",
  "description": "Description",
  "name": "Cloud project name",
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
  -d @createProject.json
  http://myserver.example.com:8080/landscaper/security/cloudproject/ -X POST
```

## Example JSON request

```
{
  "cloudProviderId": "fe8b00b5-0b1b-473a-b355-0f2294cd12b7",
  "description": "New cloud provider",
  "name": "jsmith",
      "properties": [
        {
            "name": "functionalId",
            "value": "jsmith",
            "secure": "false"
        },
        {
            "name": "functionalPassword",
            "value": "passw0rd",
            "secure": true
        }
    ]
}
```

**Parent topic:** [security/cloudproject resource](../../com.ibm.edt.api.doc/topics/security_cloudproject_.md)

