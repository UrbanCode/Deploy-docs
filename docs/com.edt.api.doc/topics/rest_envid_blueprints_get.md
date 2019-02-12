# List the blueprint that is associated with an environment

This command lists the blueprint that was used to provision an environment.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/blueprints
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "blueprintName": "myBlueprint",
    "blueprintLocation": "/landscaper/orion/file/ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent/default/myBlueprint/myBlueprint.yml",
    "blueprintUrl": "http://localhost:8080/landscaper/view/projects?open=ucdpadmin_00000000_0000_0000_0000_000000000002-OrionContent/default/myBlueprint/myBlueprint.yml"
    }
]
```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

