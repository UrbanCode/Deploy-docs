# List the object storage buckets on the cloud

This command returns Object Storage entries, primarily to create new kinds of object storage buckets such as OpenStack Swift or Amazon S3.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/objectBuckets
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/objectBuckets
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "status": "in-use",
    "size": 8,
    "name": "vol1",
    "zone": "us-east-1b",
    "id": "vol2",
    "icon": "images/editor/Volume_Palette.gif",
    "category": "storage"
  },
  {
    "status": "in-use",
    "size": 8,
    "name": "vol2",
    "zone": "us-east-1b",
    "id": "vol2",
    "icon": "images/editor/Volume_Palette.gif",
    "category": "storage"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.ibm.edt.api.doc/topics/rest_cloud.md)

