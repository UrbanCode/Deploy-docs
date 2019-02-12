# Get the value of a custom property on a component

## Request

```
GET https://{hostname}:{port}
    /cli/component/getProperty?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the property|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

Related CLI command: [getComponentProperty](udclient_getcomponentproperty.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

