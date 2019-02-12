# Update an environment

This command updates an environment by applying a blueprint to it.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/environment/{environmentId}
Accept: application/json
Content-Type: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|
|environmentId|string|true|ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "configuration": "Configuration name (Optional)",
  "environmentName": "Environment name",
  "parameters": {"name": "value (Optional - repeat as 
  necessary"},
  "teamMappings": "Array of team ids (Optional)",
  "validate": "Boolean - whether or not to validate the 
  data (Optional - default is false)"
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  environment/2f668770-aeb1-4648-891c-c97776f76a9d
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -H 'Content-Type: application/json'
  -H "Accept: application/json"
  -d @updateBlueprint.json
  -X PUT
```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

