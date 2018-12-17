# List cloud providers

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudprovider/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/security/cloudprovider/
```

## Example response

```
[
    {
        "dateCreated": 1406666374772,
        "description": "",
        "id": "a06832c2-cb76-465d-b33b-c123423490",
        "name": "Amazon",
        "properties": [
            {
                "id": "39723aa6-c8b9-45fa-8920-7cb1bb23432aaf",
                "label": "",
                "name": "orchestrationEngineUrl",
                "secure": false,
                "value": ""
            },
            {
                "id": "6823466-5d4e-4dfb-9c51-374d16f9306f",
                "label": "",
                "name": "timeoutMins",
                "secure": false,
                "value": "10"
            },
            {
                "id": "423422c-7f02-4a90-8d56-66bfa4fd6052",
                "label": "",
                "name": "url",
                "secure": false,
                "value": "http://localhost:5000/v2.0/"
            },
            {
                "id": "1234cdbc-62f7-4ab3-90b1-4b019a2d0df8",
                "label": "",
                "name": "useDefaultOrchestration",
                "secure": false,
                "value": "true"
            }
        ],
        "readOnly": false,
        "type": "AMAZON"
    },
    {
        "dateCreated": 1406666208932,
        "description": "",
        "id": "fe8b00b5-2343-473a-b355-0f2294cd12b7",
        "name": "OS 104",
        "properties": [
            {
                "id": "212f4dac-eeee-4bc6-9031-0dc2c2343245c6",
                "label": "",
                "name": "authentication_realm_id",
                "secure": false,
                "value": "e3abe6f2423d-69d1-4f45-8b1b-edd7d64495e4"
            }
        ],
        "readOnly": true,
        "type": "AUTH_REALM"
    }
]
```

**Parent topic:** [security/cloudprovider resource](../../com.ibm.edt.api.doc/topics/security_cloudprovider_.md)

