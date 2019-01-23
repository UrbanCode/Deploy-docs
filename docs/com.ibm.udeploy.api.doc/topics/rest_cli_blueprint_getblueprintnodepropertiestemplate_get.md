# Get blueprint properties

This command returns a JSON template of the properties that are required to provision a blueprint.

## Request

```
GET https://{hostname}:{port}
    /cli/blueprint/getBlueprintNodePropertiesTemplate?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|Name or ID of the blueprint|
|application|string|false|Name of the application; this parameter is required if you specify the blueprint name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getBlueprintNodePropertiesTemplate](udclient_getblueprintnodepropertiestemplate.md).

**Parent topic:** [blueprint resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_blueprint.md)

