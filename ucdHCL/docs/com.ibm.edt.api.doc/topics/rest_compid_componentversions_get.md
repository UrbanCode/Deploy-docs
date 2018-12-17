# List the versions of a component

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{componentId}/componentVersions
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|componentId|string|true|The ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/123ABC/componentVersions
```

## Example response

```
[
    {
        "ComponentId": "123ABC",
        "description": "",
        "id": "11cbd339-e64e-212a-859e-457d55b8255f",
        "name": "1.0",
        "type": "FULL"
    }
]
```

**Parent topic:** [rest/component resource](../../com.ibm.edt.api.doc/topics/rest_component.md)

