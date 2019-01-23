# List the routers for a cloud type

This command lists the routers on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/routers/blueprint/{blueprint}/configuration/{configuration}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|The blueprint ID|
|configuration|string|true|The configuration file ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  routers/blueprint/MyBlueprint/
  configuration/MyConfigOpenStack
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

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

