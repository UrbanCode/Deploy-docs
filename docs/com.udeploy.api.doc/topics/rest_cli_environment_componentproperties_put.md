# Set a component environment property value

This command will set a component property value specifically for this environment.

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/componentProperties
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
  "component": "Name or ID of the component",
  "environment": "Name or ID of the environment",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)"
}

```

Related CLI command: [setComponentEnvironmentProperty](udclient_setcomponentenvironmentproperty.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

