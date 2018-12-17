# Create a blueprint designer integration from a JSON file

## Request

```
PUT https://{hostname}:{port}
    /cli/patternIntegrationProviderCLI/createBlueprint
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "description": "Description",
  "name": "Blueprint Designer name or ID",
  "properties": {
    "landscaperPassword": "Landscaper password if 
  useAdminCredentials is true",
    "landscaperUrl": "URL of Landscaper server",
    "landscaperUser": "Landscaper username if 
  useAdminCredentials is true",
    "useAdminCredentials": "Boolean value true/false"
  }
}

```

Related CLI command: [createBlueprintDesignerIntegration](udclient_createblueprintdesignerintegration.md).

**Parent topic:** [patternIntegrationProviderCLI resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_patternintegrationprovidercli.md)

