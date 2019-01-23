# Create a cloud provider

This command creates a cloud provider from the supplied JSON string.

## Request

```
POST http://{hostname}:{port}
  /landscaper/security/cloudprovider/
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
  "description": "Description",
  "name": "Cloud provider name",
  "properties": [{
    "name": "Property name",
    "value": "Property value"
  }],
  "type": "The type of cloud provider"
}

```

## Example

```
curl -u jsmith:passwd 
   -H 'Content-Type: application/json'
  -d @createProvider.json
  http://myserver.example.com:8080/landscaper/security/cloudprovider/ -X POST
```

## Example JSON request

```
{
  "description": "Cloud provider from REST",
  "name": "New cloud provider",
  "properties": [
    {
      "id": "71531286-bab0-428b-aa91-97243dacd695",
      "label": "",
      "name": "orchestrationEngineUrl",
      "secure": false,
      "value": "http://openstack.example.com:8004"
    },
    {
      "id": "787c87c6-ae69-428a-9226-23457fee6993",
      "label": "",
      "name": "timeoutMins",
      "secure": false,
      "value": "10"
    },
    {
      "id": "9b2e3dab-9f38-232c-87e5-7a95379becff",
      "label": "",
      "name": "url",
      "secure": false,
      "value": "http://localhost:5000/v2.0/"
    },
    {
      "id": "14692f9d-5b91-4e72-55db-8fca87c112f4",
      "label": "",
      "name": "useDefaultOrchestration",
      "secure": false,
      "value": "false"
    }
  ],
  "type": "AUTH_REALM"
}
```

**Parent topic:** [security/cloudprovider resource](../../com.ibm.edt.api.doc/topics/security_cloudprovider_.md)

