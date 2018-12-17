# Set a property on a resource

## Request

```
PUT https://{hostname}:{port}
    /cli/resource/setProperty
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application (Required 
  to look up blueprint by name)",
  "blueprint": "Name or ID of the blueprint (optional)",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "resource": "ID of resource or Path to the resource, 
  such as /ResourceGroup/Agents/Agent1",
  "template": "Name or ID of the resource template 
  (optional)",
  "value": "New value for the property (optional)"
}

```

## Example response

```
{
  "id": "bd20924e-8547-4d41-b9b1-36b41278d224",
  "name": "property1",
  "value": "value1",
  "secure": false
}
```

Related CLI command: [setResourceProperty](udclient_setresourceproperty.md).

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

