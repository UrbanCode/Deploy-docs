# Delete a blueprint

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}
Accept: text/plain
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint
  -X DELETE
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
```

## Example response

**Note:** If the command returns only a response code of 200 and no JSON, the blueprint was deleted successfully.

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

