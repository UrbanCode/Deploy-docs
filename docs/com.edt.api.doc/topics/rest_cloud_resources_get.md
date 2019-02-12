# List all resources on the cloud

This command returns a list of resources on the cloud with which the current user is associated.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|updateCache|string|false| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources
```

## Example response

```
[
    {
        "category": "compute",
        "icon": "images/editor/Instance_VM1.gif",
        "id": "34f6a6a9-0dd6-47c3-8ac4-cb82e250f75c",
        "name": "Linux 1.2.3"
    },
    {
        "category": "networking",
        "icon": "images/editor/Network_Internal.gif",
        "id": "6b17edbc-b664-4bc6-9c60-c5ea9a54c019",
        "name": "demo-net"
    },
    {
        "category": "component",
        "icon": "images/editor/Component.gif",
        "id": "beaca1a5-3d15-49cf-a70e-a33781d34c57",
        "name": "JPetStore-APP",
        "url": "https://ucdeploy.example.com:8443"
    },
    {
        "category": "blueprint",
        "createdBy": "admin",
        "dateCreated": 1402327793162,
        "icon": "images/editor/Blueprint_Palette.gif",
        "id": "MyBlueprint",
        "internalId": "1w853fc9-aefc-4419-9b36-88293db78925",
        "name": "BP1",
        "url": "http://ucdp.example.com:8080/landscaper/view/projects?open=MyBlueprint",
        "version": "1.0"
    }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

