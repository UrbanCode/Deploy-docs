# List the outputs of a blueprint

Use the URL query parameter "t=UC::Blueprint::name" to specify the blueprint. To specify multiple blueprints, separate additional query parameters with an ampersand \(&\).

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/outputs
Accept: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the "t=UC::Blueprint::name" query parameter is ignored. If you do not specify the location in this header, the value of the "t=UC::Blueprint::name" query parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the query parameter plus the extension .yml.|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/outputs?
  t=UC::Blueprint::MyBlueprint
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
```

## Example response

```
{
    "UC::Blueprint::MyBlueprint": {
        "blueprint_url": {
            "description": "Blueprint Origin URL",
            "value": "http://ucdp.example.com:8080/landscaper/view/projects?open=BP1"
        },
        "param_2": {
            "description": "A second output parameter",
            "value": "12345"
        }
    }
}
```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

