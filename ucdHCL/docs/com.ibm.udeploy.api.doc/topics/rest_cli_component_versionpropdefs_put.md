# Set a version property for a component

Component version properties are available to each version of the component.

## Request

```
PUT https://{hostname}:{port}
    /cli/component/versionPropDefs?{parameters}
Accept: application/json

```

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

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [setComponentVersionPropDef](udclient_setcomponentversionpropdef.md).

**Parent topic:** [component resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_component.md)

