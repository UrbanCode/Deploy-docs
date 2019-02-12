# List configuration files for a blueprint

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/configuration
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|Name or ID of the blueprint|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  configuration
```

## Example response

```
[
    {
        "createdBy": "admin",
        "dateCreated": 1402513643601,
        "id": "MyConfigAWS",
        "name": "MyConfigAWS",
        "projectName": "MyBlueprint",
        "version": "1.0"
    },
    {
        "createdBy": "admin",
        "dateCreated": 1402328528700,
        "id": "MyConfigOpenStack",
        "name": "MyConfigOpenStack",
        "projectName": "MyBlueprint",
        "version": "1.0"
    }
]
```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

