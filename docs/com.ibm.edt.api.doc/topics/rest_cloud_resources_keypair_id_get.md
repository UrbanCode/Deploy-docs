# Show information about a key

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/keypair/{id}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|id|string|true|The ID of the keypair|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  keypair/MyKey1
```

## Example response

```
[
    {
        "fingerprint": "12:34:56:58:e4:fb:fe:da:40:06:c3:04:fc:30:76:da",
        "id": "MyKey1",
        "name": "MyKey1",
        "private_key": null,
        "public_key": "ssh-rsa ABCDEF123456\n",
        "user_id": null
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

