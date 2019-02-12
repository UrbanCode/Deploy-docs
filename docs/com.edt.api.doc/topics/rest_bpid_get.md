# Get the contents of a blueprint

This command returns the contents of the blueprint in either plain text or JSON depending on the "Accept" header. By default, it returns plain text.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}
Accept: {contentType}
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|-   `text/plain`
-   `application/json`

 |true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|

## Example

```
curl -u jsmith:passwd 
   -H "Accept: application/json"
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint
```

## Example response

The response of this command is the source code of the blueprint in JSON format, similar to the code in the **Source** tab of the blueprint editor.

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

