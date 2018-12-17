# List the storage volumes for a cloud type

This command lists the storage volumes on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/volumes/blueprint/{blueprint}/configuration/{configuration}
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
  volumes/blueprint/MyBlueprint/configuration/MyConfigOpenStack
```

## Example response

```
[
    {
        "attachments": [
            {}
        ],
        "availabilityZone": "nova",
        "category": "storage",
        "createdAt": "2014-05-31T20:11:50.000000",
        "displayDescription": null,
        "displayName": MyVolume1",
        "icon": "images/editor/Volume_Palette.gif",
        "id": "e3244376-613b-4b53-983a-8e24ec892d16",
        "metadata": {
            "readonly": "False"
        },
        "name": "MyVolume1",
        "size": 40,
        "snapshotId": null,
        "status": "available",
        "volumeType": "None"
    },
    {
        "attachments": [
            {}
        ],
        "availabilityZone": "nova",
        "category": "storage",
        "createdAt": "2014-06-02T03:37:06.000000",
        "displayDescription": null,
        "displayName": "MyVolume2",
        "icon": "images/editor/Volume_Palette.gif",
        "id": "9fd82356-2058-4dda-b87b-03e339ac72c2",
        "metadata": {},
        "name": "MyVolume2",
        "size": 20,
        "snapshotId": null,
        "status": "available",
        "volumeType": "None"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

