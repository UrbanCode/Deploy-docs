# List the parameters required to provision a blueprint with a configuration file

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{blueprintId}/configuration/{configurationId}/parameters
Accept: application/json
Location: {blueprintLocation}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprintId|string|true|The name or ID of the blueprint. The command assumes that the blueprint is in the default repository and that the file has the name of the parameter value with the extension .yml. If the Location header is specified, this parameter is ignored.|
|configurationId|string|true|The name or ID of the configuration file|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|Location|string|false|The full location of the blueprint, such as `/landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml`. If you specify the location in this header, the value of the \{blueprintId\} URL parameter is ignored. If you do not specify the location in this header, the value of the \{blueprintId\} URL parameter is used instead. In this case, the command assumes that the blueprint is in the default repository and that the name of the blueprint is the \{blueprintId\} URL parameter plus the extension .yml.|
|ConfigurationLocation|string|false|The full path to the configuration file on the blueprint designer; to get the location, use the method GET rest/blueprint/\{blueprintId\}/configuration and use the location parameter of the configuration file|
|X-Region-Name|string|false|The region to provision to \(optional\); if no region is specified, this command assumes the current region for the user that submitted the command|

## Example

```
curl -u jsmith:passwd 
   -H "Accept: application/json"
  -H "Location: /landscaper/orion/file/jsmith_8a6bfff7_2c77_45db_a235_adda61ad6653-OrionContent/myTeam/myBlueprint/myBlueprint.yml"
  http://myserver.example.com:8080/landscaper/rest/
  blueprint/MyBlueprint/configuration/myConfigFile/parameters
```

## Example response

```
[
  {
    "id": "99850bbf-452a-43aa-bda2-0dee343d4859a",
    "name": "availability_zone",
    "label": "availability_zone",
    "type": "SELECT",
    "value": "my_zone",
    "required": false,
    "description": "Name of availability zone in which to create the instance",
    "allowedValues": [
      {
        "label": "internal",
        "value": "internal"
      },
      {
        "label": "my_zone",
        "value": "my_zone"
      }
    ],
    "propertyName": "availability_zone"
  },
  {
    "id": "e085fecd-9cba-485e-a1bd-f4224e227d68",
    "name": "flavor",
    "label": "flavor",
    "type": "SELECT",
    "value": "",
    "required": false,
    "description": "Flavor to be used for compute instance",
    "allowedValues": [
      {
        "label": "m1.large",
        "value": "m1.large"
      },
      {
        "label": "m1.medium",
        "value": "m1.medium"
      },
      {
        "label": "m1.small",
        "value": "m1.small"
      },
      {
        "label": "m1.tiny",
        "value": "m1.tiny"
      },
      {
        "label": "m1.xlarge",
        "value": "m1.xlarge"
      }
    ],
    "propertyName": "flavor"
  },
  {
    "id": "c1e621e7-71e2-4b6a-9000-d12a232f2111",
    "name": "key_name",
    "label": "key_name",
    "type": "SELECT",
    "value": "",
    "required": false,
    "description": "Name of key-pair to be used for compute instance",
    "allowedValues": [
      {
        "label": "example_key",
        "value": "example_key"
      },
      {
        "label": "other_key",
        "value": "other_key"
      }
    ],
    "propertyName": "key_name"
  },
  {
    "id": "c5e5e3f1-6948-4f30-9c4b-0a135e0ffa5f",
    "name": "ucd_password",
    "label": "ucd_password",
    "type": "PASSWORD",
    "value": "e9b7bd4a-0d11-4497-84ad-047454506a52",
    "required": false,
    "description": "The user credential for the IBM UrbanCode Deploy server.",
    "propertyName": "password"
  },
  {
    "id": "910181a9-7f29-4948-b28c-6328d349c8c9",
    "name": "ucd_relay_url",
    "label": "ucd_relay_url",
    "type": "VALIDATION_TEXT",
    "value": "None",
    "required": false,
    "description": "The server URL for an agent relay - leave as 'None' to enable agents to communicate with server directly."
  },
  {
    "id": "644007c0-99d6-4c0c-95c2-e3d13c725089",
    "name": "ucd_server_url",
    "label": "ucd_server_url",
    "type": "VALIDATION_TEXT",
    "value": "http://myserver.example.com:9080",
    "required": false,
    "description": "The server URL for agent communication to the IBM UrbanCode Deploy server. Do *not* add a trailing slash.",
    "propertyName": "urbancode_deploy_url"
  },
  {
    "id": "12b0a81d-ec64-49b7-abc7-ccb078a95fac",
    "name": "ucd_user",
    "label": "ucd_user",
    "type": "VALIDATION_TEXT",
    "value": "PasswordIsAuthToken",
    "required": false,
    "description": "The user credential for the IBM UrbanCode Deploy server.",
    "propertyName": "username"
  },
  {
    "id": "c3ad77b5-f6d1-4dcc-b8af-95b526af669e",
    "name": "vmware_resource_pool",
    "label": "vmware_resource_pool",
    "type": "VALIDATION_TEXT",
    "value": "TODO",
    "required": false,
    "description": "vmware_resource_pool"
  }

]

```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

