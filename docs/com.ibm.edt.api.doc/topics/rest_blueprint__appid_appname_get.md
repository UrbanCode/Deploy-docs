# List the blueprints that refer to an application

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint//applicationId/{applicationId}/applicationName/{applicationName}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|applicationName|string|true|Name of the application|
|applicationId|string|true|ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/
  applicationId/995b585e-af00-494e-a655-fa47d4b0dbee/
  applicationName/MyApplication
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "type": "blueprint",
    "application": "App",
    "location": "/landscaper/orion/file/
      ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent
      /default/myblueprint1/myblueprint1.yml",
    "id": "MyBlueprint1",
    "name": "MyBlueprint1",
    "category": "blueprint",
    "icon": "images/editor/Blueprint_icon.gif",
    "version": "1.0",
    "url": "https://designserver.example.com:8443/landscaper/view/projects?open=MyBlueprint1"
  },
  {
    "type": "blueprint",
    "application": "App",
    "location": "/landscaper/orion/file/
      ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent
      /default/myblueprint2/myblueprint2.yml",
    "id": "MyBlueprint2",
    "name": "MyBlueprint2",
    "category": "blueprint",
    "icon": "images/editor/Blueprint_icon.gif",
    "version": "1.0",
    "url": "https://designserver.example.com:8443/landscaper/view/projects?open=MyBlueprint2"
  }
]
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

