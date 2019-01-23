# Validate a blueprint

This command validates a blueprint with the parameters in a JSON string to ensure that the blueprint will deploy correctly.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/validate
Accept: application/json
Content-Type: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|
|X-Region-Name|string|false|The cloud region|

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "configuration": "Configuration file name (Optional)",
  "configurationLocation": "Configuration file location 
  (Optional)",
  "environmentId": "The ID for the environment",
  "environmentName": "Environment name",
  "parameters": {"parameter name": "parameter value 
  (Optional - repeat as necessary)"}
}

```

## Example

```
curl -u jsmith:passwd 
   -H 'Content-Type: application/json'
  -H "Accept: application/json"
  -H "X-Region-Name: us-east"
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -d @validateBlueprint.json
  -X PUT
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  validate
```

## Example JSON request

```
{
  "configuration": "myConfigFile",
  "configurationLocation":
    "/landscaper/orion/file/jsmith_00000000_0000_0000_0000_000000000002-
    OrionContent/Internal-Team/configurations/myConfigFile.yml",
  "environmentName": "MyNewEnvironment",
  "environmentId": "MyNewEnvironment",
  "parameters": {
    "key_name":"myKey",
    "flavor": "m1.medium"
  }
}

```

## Example response

**Note:** If the command returns only a response code of 200 and no JSON, the blueprint and configuration file validated successfully. The following response shows an error that means that a required parameter was not specified.

```
[
    {
        "config_file": "MyConfigOpenStack",
        "errorMessage": "Key Pair (TODO) does not exist.",
        "errorType": "error",
        "object": {
            "parameters": {
                "key_name": "TODO"
            }
        },
        "source": "configuration"
    }
]
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

