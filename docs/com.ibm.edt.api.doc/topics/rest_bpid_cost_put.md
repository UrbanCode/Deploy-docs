# Estimate the cost for a blueprint in the cloud

This command estimates the running cost of the blueprint in the selected cloud.

## Request

```
PUT http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/cost
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
  "cloudProjectId": "Cloud project ID",
  "configuration": "Configuration name (Optional)",
  "environmentName": "Environment name",
  "key_name": "Key name",
  "parameters": {"parameter_name": "parameter_value 
  (Optional - repeat as necessary"}
}

```

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/myBlueprint/cost
  -H "Accept: application/json"
  -H "Content-Type: application/json"
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  -X PUT
```

## Example JSON request

```
{
  "cloudProjectId": "a1135b32-98bb-4c2f-9269-e433bdfd9832"
}

```

## Example response

```
{
  "cost": 6,
  "instances": [
    {
      "name": "image1",
      "cost": 0.5
    },
    {
      "name": "image2",
      "cost": 0.5
    }
  ],
  "volumes": [
    {
      "name": "diskB",
      "cost": 1,
      "instance": "image2"
    },
    {
      "name": "diskA",
      "cost": 2,
      "instance": "imageA"
    }
  ],
  "components": [],
  "floatingIps": [
    {
      "name": "image1_floating_ip",
      "cost": 2
    }
  ]
}

```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

