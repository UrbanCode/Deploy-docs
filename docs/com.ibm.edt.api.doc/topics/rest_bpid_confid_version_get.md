# List the versions of a configuration file

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/configuration/{configurationId}/version
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|Name or ID of the blueprint|
|configurationId|string|true|Name or ID of the configuration file|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  configuration/MyConfigOpenStack/version
```

## Example response

```
[
    "1.0"
]
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

