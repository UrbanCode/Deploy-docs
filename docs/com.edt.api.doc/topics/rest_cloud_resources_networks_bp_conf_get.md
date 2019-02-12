# List the networks for a cloud type

This command lists the networks on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/networks/blueprint/{blueprint}/configuration/{configuration}
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
  networks/blueprint/MyBlueprint/configuration/MyConfigOpenStack
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

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

