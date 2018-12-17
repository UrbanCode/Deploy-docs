# getBlueprintNodePropertiesTemplate

Get blueprint properties

This command returns a JSON template of the properties that are required to provision a blueprint.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getBlueprintNodePropertiesTemplate [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|Name or ID of the blueprint|
|application|string|false|Name of the application; this parameter is required if you specify the blueprint name instead of ID|

Related REST command: [Get blueprint properties](rest_cli_blueprint_getblueprintnodepropertiestemplate_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

