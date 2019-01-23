# Create a component template from a JSON file

## Request

```
PUT https://{hostname}:{port}
    /cli/componentTemplate/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "componentType": "STANDARD or ZOS",
  "description": "Component template description",
  "name": "Component template name or ID",
  "properties": {"Source configuration plugin property 
  name": "Property value"},
  "sourceConfigPluginName": "Name of the source 
  configuration type"
}

```

Related CLI command: [createComponentTemplate](udclient_createcomponenttemplate.md).

**Parent topic:** [componentTemplate resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_componenttemplate.md)

