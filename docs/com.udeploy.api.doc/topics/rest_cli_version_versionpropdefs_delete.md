# Delete a component version property

## Request

```
DELETE https://{hostname}:{port}
    /cli/version/versionPropDefs?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property to delete|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [deleteComponentVersionPropDef](udclient_deletecomponentversionpropdef.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

