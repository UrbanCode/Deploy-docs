# Get cloud project property definitions for a cloud provider

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudprovider/{cloudProviderId}/projects/propdefs
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloudProviderId|string|true|ID of the cloud provider|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudprovider/fe8b22b5-0b1b-473a-2424-0f2294cd12b7/projects/propdefs
```

## Example response

```
[
    {
        "description": "The id of a user in this project.",
        "id": "bd757139-df9e-424e-8cba-60c245334572d",
        "label": "Functional ID",
        "name": "functionalId",
        "required": true,
        "type": "VALIDATION_TEXT",
        "value": ""
    },
    {
        "description": "The password for the functional ID.",
        "id": "538c75e1-aa0c-4967-892b-96553def4e",
        "label": "Password",
        "name": "functionalPassword",
        "required": true,
        "type": "SECURE",
        "value": "****"
    }
]
```

**Parent topic:** [security/cloudprovider resource](../../com.ibm.edt.api.doc/topics/security_cloudprovider_.md)

