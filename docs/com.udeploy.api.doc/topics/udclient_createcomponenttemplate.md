# createComponentTemplate

Create a component template from a JSON file

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createComponentTemplate [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "componentType": "STANDARD or ZOS",
  "description": "Component template description",
  "name": "Component template name or ID",
  "properties": {"Source configuration plugin property 
  name": "Property value"},
  "sourceConfigPluginName": "Name of the source 
  configuration type"
}

```

Related REST command: [Create a component template from a JSON file](rest_cli_componenttemplate_create_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

