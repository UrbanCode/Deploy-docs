# List the parameters required to provision a blueprint with a configuration and common configuration file

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/configuration/{configurationId}/common/{additionalConfigurationId}/parameters
Accept: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|
|additionalConfigurationId|string|true|The name or ID of the common configuration file|
|configurationId|string|true|The name or ID of the configuration file|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|
|ConfigurationLocation|string|false|The full path to the configuration file on the blueprint designer; to get the location, use the method GET rest/blueprint/\{blueprintId\}/configuration and use the location parameter of the configuration file|
|AdditionalConfigurationLocation|string|false|The full path to the common configuration file on the blueprint designer;|
|X-Region-Name|string|false|The region to provision to \(optional\); if no region is specified, this command assumes the current region for the user that submitted the command|

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

