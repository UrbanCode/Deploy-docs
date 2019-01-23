# Get cloud projects for a cloud provider

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudprovider/{cloudProviderId}/projects
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
  http://myserver.example.com:8080/landscaper/security/cloudprovider/fe8b22b5-0b1b-473a-2424-0f2294cd12b7/projects
```

## Example response

```
[
    {
        "cloudProviderId": "fe8b22b5-0b1b-473a-2424-0f2294cd12b7",
        "dateCreated": 1406667798199,
        "description": "",
        "displayName": "Jdoe@Amazon",
        "id": "d92343ce-4e6e-4271-bfbb-18c28ac674b7",
        "name": "jdoe",
        "properties": [
            {
                "id": "b6422b3f-7486-419b-82c5-9b73980db6c2",
                "label": "",
                "name": "accessId",
                "secure": false,
                "value": "jdoe"
            },
            {
                "id": "950247cf-2434-42ae-bd78-db6cf111b726",
                "label": "",
                "name": "functionalId",
                "secure": false,
                "value": "deleteme"
            },
            {
                "id": "0c756f1a-5897-465b-a665-90354b3ef3ac",
                "label": "",
                "name": "functionalPassword",
                "secure": true,
                "value": "****"
            },
            {
                "id": "3067c55e-aabb-40bf-a71e-6f3f7466056c",
                "label": "",
                "name": "secretKey",
                "secure": false,
                "value": "12345"
            }
        ],
        "readOnly": false,
        "type": "AMAZON"
    },
    {
        "cloudProviderId": "fe8b22b5-0b1b-473a-2424-0f2294cd12b7",
        "dateCreated": 1406666392494,
        "description": "",
        "displayName": "Jsmith@Amazon",
        "id": "ebb4232a-d89f-4802-ae63-85248a085102",
        "name": "Jsmith",
        "properties": [
            {
                "id": "0c23fa5c-b2a2-4b8b-85b3-61453d4ce6ae",
                "label": "",
                "name": "accessId",
                "secure": false,
                "value": "12345"
            },
            {
                "id": "f8521629-4242-4c56-9e2b-12f58c537a9e",
                "label": "",
                "name": "functionalId",
                "secure": false,
                "value": "67890"
            },
            {
                "id": "8661991b-1414-4d60-8392-ba6187048bc7",
                "label": "",
                "name": "functionalPassword",
                "secure": true,
                "value": "****"
            },
            {
                "id": "66a5e9b2-c1c8-4af4-5514-86f6949d5e8a",
                "label": "",
                "name": "secretKey",
                "secure": false,
                "value": "qwerty"
            }
        ],
        "readOnly": false,
        "type": "AMAZON"
    }
]
```

**Parent topic:** [security/cloudprovider resource](../../com.ibm.edt.api.doc/topics/security_cloudprovider_.md)

