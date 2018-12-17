# List applications

This command lists the applications on the connected IBM UrbanCode Deploy server.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/applications
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/applications
```

## Example response

```
[
    {
        "description": "",
        "id": "3f8945cc-248e-4512-b616-4edc5ad12a2f",
        "name": "JPetStore",
        "teamMappings": []
    },
    {
        "description": "",
        "id": "0bfe1a6c-fd79-23af-a1e7-6db3ae193345",
        "name": "Another application",
        "teamMappings": []
    }
]
```

**Parent topic:** [rest/component resource](../../com.ibm.edt.api.doc/topics/rest_component.md)

