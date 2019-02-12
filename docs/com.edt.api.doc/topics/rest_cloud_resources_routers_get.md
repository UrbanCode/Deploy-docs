# List the routers on the cloud

This command returns a list of the routers on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/routers
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  routers
```

## Example response

```
[
    {
        "category": "networking",
        "icon": "images/editor/Network_Internal.gif",
        "id": "3dgd67ae-eea6-4954-ad6c-3fe47246a227",
        "name": "ext-to-int"
    },
    {
        "category": "networking",
        "icon": "images/editor/Network_Internal.gif",
        "id": "f3f9d345-216b-4a99-a47f-dd0620af535d",
        "name": "multicloud-network"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

