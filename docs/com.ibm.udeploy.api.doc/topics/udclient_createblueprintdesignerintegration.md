# createBlueprintDesignerIntegration

Create a blueprint designer integration from a JSON file

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createBlueprintDesignerIntegration [JSON file]
```

## Parameters

None.

## Template

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

Related REST command: [Create a blueprint designer integration from a JSON file](rest_cli_patternintegrationprovidercli_createblueprint_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

