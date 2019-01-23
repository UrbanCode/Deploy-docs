# Provision a blueprint

This command provisions a blueprint to the cloud along with the parameters in the submitted JSON string.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/deploy
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
  "additionalConfiguration": "A secondary configuration 
  name (Optional)",
  "additionalConfigurationLocation": "A secondary 
  configuration location (Optional)",
  "cloudProjectId": "Cloud project ID (Optional - default 
  is the user's current cloud project)",
  "configuration": "Configuration name (Optional)",
  "configurationLocation": "Configuration location 
  (Optional)",
  "environmentName": "Environment name",
  "parameters": {"name": "value (Optional - repeat for 
  each parameter)"},
  "region": "Region name (Optional - default is the user's 
  current region)",
  "teamMappings": "Array of UCD team ids (Optional)",
  "validate": "Boolean - whether or not to validate the 
  data (Optional - default is false)"
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  deploy
  -H 'Content-Type: application/json'
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -d @deployBlueprint.json
  -X PUT
```

**Note:** To specify a region for the environment, include the region in the X-Region-Name header parameter, as in this example:

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  deploy
  -H 'Content-Type: application/json'
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -H 'X-Region-Name: MyCloudRegion'
  -d @deployBlueprint.json
  -X PUT
```

## Example JSON request

```
{
  "environmentName": "myNewEnvironment1",
  "configuration": "myConfigFile",
  "cloudProjectId":"3d16879f-7b43-4909-9862-12767dad7f04",
  "configurationLocation":"/landscaper/orion/file/jsmith_00000000_2-OrionContent/default/configurations/myConfigFile.yml",
  "parameters": {
    "availability_zone" : "nova",
    "flavor" : "m1.tiny",
    "key_name" : "myKey",
    "ucd_password":"cc99a431-d96c-4154-99d6-1a5532275015",
    "ucd_relay_url":"None",
    "ucd_server_url":"http://ucd.example.com:9080",
    "ucd_user":"PasswordIsAuthToken"
  },
  "teamMappings":[],
  "validate": "true"
}
```

## Example response

```
{
  "id": "08df12323-fb35-4d63-8937-d78ea3c5efcb",
  "links": [
    {
      "href": "http://ucdp.example.com:8004/v1/1234/stacks/
  NewEnvironment/08df1414-aac5-4d63-8937-d78ea3c5efcb",
      "rel": "self"
    }
  ]
}
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

