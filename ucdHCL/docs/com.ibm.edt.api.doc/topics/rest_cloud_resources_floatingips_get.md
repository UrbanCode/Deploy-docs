# List the floating IP addresses on the cloud

This command returns a list of the floating IP addresses on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/floatingIPs
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/floatingIPs
```

## Example response

```
[
    {
        "id": "34f0efe0-05d9-420c-922b-883d5b06cafa",
        "name": "10.10.164.37"
    },
    {
        "id": "1ef7858e-66c7-547c-824b-38faa1b2be8f",
        "name": "10.10.164.60"
    }]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

