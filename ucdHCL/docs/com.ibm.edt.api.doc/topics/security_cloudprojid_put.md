# Update a cloud project

This command updates a cloud project from the supplied JSON string

## Request

```
PUT http://{hostname}:{port}
  /landscaper/security/cloudproject/{cloudProjectId}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloudProjectId|string|true|ID of the cloud project|

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
  -d @updateProject.json
  http://myserver.example.com:8080/landscaper/security/cloudproject/1241aa10-5f98-4f11-be63-b21ad69c3e4b -X PUT
```

## Example JSON request

```
{
  "cloudProviderId": "fe8b00b5-0b1b-473a-b355-0f2294cd12b7",
  "description": "Updated cloud project",
  "name": "My updated cloud project",
      "properties": [
        {
            "name": "functionalId",
            "value": "admin",
            "secure": "false"
        },
        {
            "name": "functionalPassword",
            "value": "password",
            "secure": true
        }
    ]
}
```

**Note:** The properties that you put in the JSON request overwrite all of the properties on the cloud project.

**Note:** You must specify the cloud provider ID in the JSON request, but you cannot change the cloud provider.

**Parent topic:** [security/cloudproject resource](../../com.ibm.edt.api.doc/topics/security_cloudproject_.md)

