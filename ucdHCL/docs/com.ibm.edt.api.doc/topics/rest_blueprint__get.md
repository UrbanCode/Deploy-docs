# List blueprints

This command lists all blueprints that you have access to.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/
```

## Example response

```
[
    {
        "category": "blueprint",
        "createdBy": "jsmith",
        "dateCreated": 1405958418154,
        "icon": "images/editor/Blueprint_Palette.gif",
        "id": "Blueprint1",
        "internalId": "7eb267e6-1efe-4b7a-a47e-6532f52d50f2",
        "name": "Blueprint1",
        "url": "http://ucdp.example.com:8080/landscaper/view/projects?open=Blueprint1",
        "version": "1.0"
    },
    {
        "category": "blueprint",
        "createdBy": "jsmith",
        "dateCreated": 1405967697007,
        "icon": "images/editor/Blueprint_Palette.gif",
        "id": "Blueprint2",
        "internalId": "b1071f0b-7e7f-472a-a828-524ad78df1d6",
        "name": "Blueprint2",
        "url": "http://ucdp.example.com:8080/landscaper/view/projects?open=Blueprint2",
        "version": "1.0"
    }
]
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

