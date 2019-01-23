# List the networks on the cloud

This command returns a list of the networks on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/networks
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/networks
```

## Example response

```
[
    {
        "category": "networking",
        "icon": "images/editor/Network_Internal.gif",
        "id": "12345",
        "name": "net-1"
    },
    {
        "category": "networking",
        "icon": "images/editor/Network_External.gif",
        "id": "67890",
        "name": "net-2"
    },
    {
        "category": "networking",
        "icon": "images/editor/Network_Internal.gif",
        "id": "24680",
        "name": "net-3"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

