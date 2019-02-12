# Update a blueprint

This command updates a blueprint from the supplied JSON string. The JSON string must include the contents of the blueprint in the "document" attribute.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}
Accept: application/json
Content-Type: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|

This command takes a JSON request string or file. Use the following template for the request:

```
{"document": "Blueprint contents"}

```

## Example

```
curl -u jsmith:passwd 
   -H "Content-Type: application/json"
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint 
  -X PUT 
  -d @updatedBlueprint.json
```

## Example JSON request

```
{
    "document": "heat_template_version: 2013-05-23\n\ndescription: >\n  
My blueprint.\n\nparameters:\n  flavor:\n    type: string\n    
description: Flavor to be used for compute instance\n    
default: \"m1.small\"\n  key_name:\n    type: string\n    
description: Name of key-pair to be used for compute instance\n    
default: \"TODO\"\n\nresources:\n  ubuntu-precise:\n    
type: OS::Nova::Server\n    properties:\n      name: \"linux-os\"\n      
image: \"10974a7d-483b-438d-92e5-1d2b6afc799b\" # linux-os\n      
flavor: { get_param: flavor }\n      key_name: { get_param: key_name }
\n\n\noutputs:\n  blueprint_url:\n    description: Blueprint Origin URL\n    
value:  http://ucdp.example.com:8080/landscaper/view/projects
?open=MyBlueprint\n\n"
}
```

## Example response

The response of this command is the source code of the blueprint in JSON format, similar to the code in the **Source** tab of the blueprint editor.

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

