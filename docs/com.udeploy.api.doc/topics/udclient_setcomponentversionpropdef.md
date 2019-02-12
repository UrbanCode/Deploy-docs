# setComponentVersionPropDef

Set a version property for a component

Component version properties are available to each version of the component.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setComponentVersionPropDef [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property to set|
|description|string|false|Description of the property|
|required|string|false|Whether the property is a required value on versions \(true/false, optional - defaults to false\)|
|label|string|false|Label for the property when presented in forms. \(Optional. Defaults to the name.\)|
|value|string|false|Default value of the property definition|
|allowedValues|string|false|Comma separated list of allowed values in SELECT or MULTI\_SELECT properties|
|pattern|string|false|A regular expression to enforce that values for this property match a certain pattern. Leave blank to allow any values.|
|type|string|false|The type of property definition; valid values are TEXT \(the default\), , TEXTAREA, CHECKBOX, SELECT, MULTI\_SELECT, DATETIME, and SECURE|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setComponentVersionPropDef 
  -component JPetStore-APP 
  -name Prop1 
  -value true 
  -type CHECKBOX
```

## Example response

```
{
  "id": "870bc2f5-55e2-4cb9-b3ab-f750688754b9",
  "name": "Prop1",
  "type": "CHECKBOX",
  "value": "prop1",
  "required": false
}
```

Related REST command: [Set a version property for a component](rest_cli_component_versionpropdefs_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

