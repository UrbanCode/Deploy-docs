# List cloud projects

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudproject/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudproject/
```

## Example response

```
[
    {
        "cloudProviderId": "fe8b00b5-0b1b-473a-b355-2312394cd12b7",
        "dateCreated": 1406666213336,
        "description": "",
        "displayName": "JSmith@My OpenStack server",
        "id": "1241aa10-5f98-4f11-be63-b21ad69c3e4b",
        "name": "JSmith",
        "properties": [],
        "readOnly": true,
        "type": "AUTH_REALM"
    },
    {
        "cloudProviderId": "a2234432c2-cb76-465d-b33b-c1ae869fe190",
        "dateCreated": 1406666392494,
        "description": "",
        "displayName": "JSmith@Amazon",
        "id": "2344a10a-d89f-4802-ae63-85248a085102",
        "name": "JSmith",
        "properties": [
            {
                "id": "0ce9fa5c-b2a2-4b8b-85b3-245213d4ce6ae",
                "label": "",
                "name": "accessId",
                "secure": false,
                "value": "12345"
            },
            {
                "id": "f8242629-c38c-4c56-9e2b-12f58c537a9e",
                "label": "",
                "name": "functionalId",
                "secure": false,
                "value": "JSmith"
            },
            {
                "id": "8663491b-297f-4d60-8392-ba6187048bc7",
                "label": "",
                "name": "functionalPassword",
                "secure": true,
                "value": "****"
            },
            {
                "id": "22a5e9b2-c1c8-4af4-8f8b-86f6949d5e8a",
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

**Parent topic:** [security/cloudproject resource](../../com.edt.api.doc/topics/security_cloudproject_.md)

