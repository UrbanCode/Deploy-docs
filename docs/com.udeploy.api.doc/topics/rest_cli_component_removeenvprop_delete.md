# Delete a component environment property

## Request

```
DELETE https://{hostname}:{port}
    /cli/component/removeEnvProp?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property to remove|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/component/
  removeEnvProp?name=MyProperty&component=d2e59ca4-a2f5-4851-9c85-629c1019ba20"
  -X DELETE
```

Related CLI command: [removeEnvironmentProperty](udclient_removeenvironmentproperty.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

