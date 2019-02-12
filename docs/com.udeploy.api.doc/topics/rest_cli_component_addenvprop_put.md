# Create a component environment property

## Request

```
PUT https://{hostname}:{port}
    /cli/component/addEnvProp?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|name|string|true|Name of the property|
|component|string|true|ID of the component|
|label|string|false|Label of the property|
|default|string|false|Default value|
|description|string|false|Description for the property|
|required|boolean|false|Whether the property is required|
|pattern|string|false|A regular expression that specifies valid values for the property|
|secure|boolean|false|Specify true to create a secure property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/component/
  addEnvProp?name=MyProperty&component=d2e59ca4-a2f5-4851-9c85-629c1019ba20
  &default=DefaultValue&required=true" 
  -X PUT
```

Related CLI command: [addEnvironmentProperty](udclient_addenvironmentproperty.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

