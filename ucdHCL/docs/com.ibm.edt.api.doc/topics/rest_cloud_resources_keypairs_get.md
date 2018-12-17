# List the keys on the cloud

This command returns a list of the keys on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/keypairs
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/keypairs
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
    },
    {
        "fingerprint": "78:90:12:96:3d:69:6a:58:94:0c:ba:f5:03:bb:0c",
        "id": "MyKey1",
        "name": "MyKey1",
        "private_key": null,
        "public_key": "ssh-rsa 123456ABCDEF\n",
        "user_id": null
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

