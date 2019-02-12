# List the images on the cloud

This command returns a list of the images on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/images?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|visibility|string|false| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/images
```

## Example response

```
[
    {
        "category": "compute",
        "icon": "images/editor/Instance_Generic.gif",
        "id": "56781f5-f675-468f-894d-2e700cd81f79",
        "name": "Linux image 1"
    },
    {
        "category": "compute",
        "icon": "images/editor/Instance_Generic.gif",
        "id": "6f60f6e1-3bc9-331d-9b6e-2dd8a28a3253",
        "name": "Linux image 2"
    },
    {
        "category": "compute",
        "icon": "images/editor/Instance_Generic.gif",
        "id": "bdf5549c-892f-4c67-a3c9-9f494f1c7ead",
        "name": "Linux image 3"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

