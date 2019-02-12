# Get information about a cloud provider

## Request

```
GET http://{hostname}:{port}
  /landscaper/security/cloudprovider/{cloudProviderId}
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
  http://myserver.example.com:8080/landscaper/security/cloudprovider/fe8b00b5-0b1b-473a-2462-0f2294cd12b7
```

## Example response

```
{
    "dateCreated": 1406666208932,
    "description": "",
    "id": "fe8b00b5-0b1b-473a-2462-0f2294cd12b7",
    "name": My OpenStack server",
    "properties": [
        {
            "id": "212f4dac-ff34-4bc6-9031-0dc2c23405c6",
            "label": "",
            "name": "authentication_realm_id",
            "secure": false,
            "value": "e323426fd-69d1-4f45-8b1b-edd7d68295e4"
        }
    ],
    "readOnly": true,
    "type": "AUTH_REALM"
}
```

**Parent topic:** [security/cloudprovider resource](../../com.edt.api.doc/topics/security_cloudprovider_.md)

