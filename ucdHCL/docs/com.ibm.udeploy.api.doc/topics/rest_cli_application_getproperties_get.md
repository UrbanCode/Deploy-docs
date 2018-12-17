# Get all application properties and their values.

## Request

```
GET https://{hostname}:{port}
    /cli/application/getProperties?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application/getProperties
  ?application=JPetStore"
```

## Example response

```
[
  {
    "id": "8b383d28-f64f-4f94-8ea1-1e85a323f527",
    "name": "Prop1",
    "value": "value1",
    "description": "",
    "secure": false
  },
  {
    "id": "e3a54008-6c73-4c72-b197-72b830b2ac6d",
    "name": "Prop2",
    "value": "value2",
    "description": "",
    "secure": false
  },
  {
    "id": "cce49826-a236-4bee-a8f4-cd015f2a6e8b",
    "name": "Prop3",
    "value": "value3",
    "description": "",
    "secure": false
  }
]
```

Related CLI command: [getApplicationProperties](udclient_getapplicationproperties.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

