# Get component environment properties for an environment

These properties are defined on the component and their values are set on the environment.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/componentProperties?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|component|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "c598738e-2057-44d7-aee7-e805df40cc69",
    "name": "Environment property 1",
    "value": "false",
    "description": "",
    "secure": false
  }
]
```

Related CLI command: [getComponentEnvironmentProperties](udclient_getcomponentenvironmentproperties.md).

**Parent topic:** [environment resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment.md)

