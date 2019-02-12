# Delete a blueprint designer integration

## Request

```
DELETE https://{hostname}:{port}
    /cli/patternIntegrationProviderCLI/deleteBlueprint?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|patternIntegration|string|true|UUID or Name of the Blueprint Pattern Integration|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

Related CLI command: [deleteBlueprintDesignerIntegration](udclient_deleteblueprintdesignerintegration.md).

**Parent topic:** [patternIntegrationProviderCLI resource](../../com.udeploy.api.doc/topics/rest_cli_patternintegrationprovidercli.md)

