# Set a property on a component

## Request

```
PUT https://{hostname}:{port}
    /cli/component/propValue
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Name or ID of the component",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "value": "Value of the property (optional)"
}

```

## Example response

```
{
  "id": "3702f391-09e1-4550-903a-d5ae286c94aa",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related CLI command: [setComponentProperty](udclient_setcomponentproperty.md).

**Parent topic:** [component resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_component.md)

