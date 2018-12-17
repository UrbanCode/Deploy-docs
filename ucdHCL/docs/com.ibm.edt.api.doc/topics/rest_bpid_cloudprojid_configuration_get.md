# List configuration files for a blueprint and the specified cloud

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/cloudproject/{cloudprojectId}/configuration
Accept: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|
|cloudprojectId|string|true|ID of the cloud project|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/myBlueprint/
  cloudproject/00000000-0000-0000-9999-000000000003/configuration
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "id": "OS_config_1",
    "name": "OS_config_1",
    "category": "configuration",
    "location": "/landscaper/orion/file/
      jsmith_00000000_0000_0000_0000_000000000002-OrionContent
      /default/configurations/OS_config_1.yml",
    "version": "1.0"
  },
  {
    "id": "OS_config_2",
    "name": "OS_config_2",
    "category": "configuration",
    "location": "/landscaper/orion/file/
      jsmith_00000000_0000_0000_0000_000000000002-OrionContent
      /default/configurations/OS_config_2.yml",
    "version": "1.0"
  }
]
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

