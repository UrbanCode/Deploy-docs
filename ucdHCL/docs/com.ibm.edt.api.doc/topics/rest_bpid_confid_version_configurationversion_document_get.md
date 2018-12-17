# Get a configuration file

This command returns a JSON representation of a specific version of a configuration file. You specify the configuration file in the Location header.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/configuration/{configurationId}/version/{configurationVersion}/document
Accept: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|configurationVersion|string|true|Name of the version of the configuration file|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|
|configurationId|string|true|Name or ID of the configuration file|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|Location|string|false|The full location of the configuration file to use, such as `/landscaper/orion/file/jsmith_00000000_2-OrionContent/default/configurations/my_config.yml`.|

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/blueprint/MyBlueprint/
  configuration/MyConfigOpenStack/
  version/1.0/document
```

## Example response

```
{
    "parameters": {
        "flavor": "m1.small",
        "key_name": "TODO",
        "network_id_demo-net": "6b174235-b664-4bc6-9c60-c5ea9a54c019",
        "public_network_id": "demo-net",
        "server_url": "http://ucdp.example.com:8080/landscaper",
        "ucd_password": "TODO",
        "ucd_server_url": "https://ucdserver.example.com:8443",
        "ucd_user": "admin"
    }
}
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

