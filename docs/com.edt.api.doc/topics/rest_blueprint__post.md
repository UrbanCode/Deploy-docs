# Create a blueprint

This command creates a blueprint from the supplied JSON string.

## Request

```
POST http://{hostname}:{port}
  /landscaper/rest/blueprint/
Accept: application/json
Content-Type: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "description": "Description",
  "name": "Blueprint name"
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/
  blueprint/ 
  -H "Accept: application/json"
  -H "Content-Type: application/json"
  -d @newBlueprint.json
```

## Example JSON request

```
{
  "description": "My new blueprint",
  "name": "NewBlueprint"
}

```

## Example response

```
{
  "id": "Restblueprint",
  "name": "Restblueprint",
  "location": "/landscaper/orion/file/ucdpadmin_02-OrionContent/default/Restblueprint/Restblueprint.yml",
  "document": "heat_template_version: 2013-05-23
  \n\ndescription: >\n  New blueprint from rest
  \n\nresources:\n\noutputs:\n  blueprint_url:\n    
  description: Blueprint Origin URL\n    
  value:  https://192.168.77.54:8443/landscaper/view/projects?
  open=ucdpadmin_02-OrionContent/default/Restblueprint/Restblueprint.yml\n\n"
}
```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

