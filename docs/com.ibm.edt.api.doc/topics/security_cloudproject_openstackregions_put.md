# Get the list of OpenStack regions for a cloud project

This command gets the OpenStack regions for a cloud project

## Request

```
PUT http://{hostname}:{port}
  /landscaper/security/cloudproject/openstackRegions
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
  "name": "OpenStack project name",
  "properties": [
    {
      "name": "functionalId",
      "secure": false,
      "value": "A Keystone user"
    },
    {
      "name": "functionalPassword",
      "secure": true,
      "value": "Password for the user"
    },
    {
      "name": "domain",
      "secure": false,
      "value": "Domain for the user"
    }
  ]
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/
  cloudproject/openstackRegions
  -H "Accept: application/json" 
  -X PUT 
  -d @myCloudProject.json
```

## Example JSON request

```
{
  "name": "myCloudProject",
  "cloudProviderId": "64a41dc3-7cfe-437b-8ac2-3918344395ee",
  "properties": [{
    "name": "functionalId",
    "value": "myAccountID",
    "secure": false
  }, {
    "name": "functionalPassword",
    "value": "abc12345",
    "secure": true
  }, {
    "name": "domain",
    "value": "default",
    "secure": false
  }]
}
```

## Example response

```
[{"id":"region1","name":"region1"}]
```

**Parent topic:** [security/cloudproject resource](../../com.ibm.edt.api.doc/topics/security_cloudproject_.md)

