# Set a property on environment

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/propValue
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application; this 
  value is required if you specify the environment name 
  instead of ID",
  "environment": "Name or ID of the environment",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)"
}

```

## Example response

```
{
  "id": "ba3f8bd4-c26e-4529-a2a3-66e283242244",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related CLI command: [setEnvironmentProperty](udclient_setenvironmentproperty.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

