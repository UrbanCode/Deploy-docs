# Delete a cloud provider

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/security/cloudprovider/{cloudProviderId}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|cloudProviderId|string|true|ID of the cloud provider|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudprovider/fe8b00b5-0b1b-473a-b355-2312394cd12b7/projects/propdefs
```

## Example response

```
[
    {
        "description": "The id of a user in this project.",
        "id": "1ed62e3e-48f3-4eb7-9b59-b8f23230b53b",
        "label": "Functional ID",
        "name": "functionalId",
        "required": true,
        "type": "VALIDATION_TEXT",
        "value": ""
    },
    {
        "description": "The password for the functional ID.",
        "id": "55812a90-c61f-4df6-b684-345113184b",
        "label": "Password",
        "name": "functionalPassword",
        "required": true,
        "type": "SECURE",
        "value": "****"
    }
]
```

**Parent topic:** [security/cloudprovider resource](../../com.edt.api.doc/topics/security_cloudprovider_.md)

