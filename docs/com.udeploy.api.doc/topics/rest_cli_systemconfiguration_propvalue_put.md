# Set a system property

System properties behave like global variables for the server.

## Request

```
PUT https://{hostname}:{port}
    /cli/systemConfiguration/propValue
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
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
  "id": "f3bec2ee-3f3e-461f-b5b0-e844efafbdbe",
  "name": "System property 1",
  "value": "value001",
  "secure": false
}
```

Related CLI command: [setSystemProperty](udclient_setsystemproperty.md).

**Parent topic:** [systemConfiguration resource](../../com.udeploy.api.doc/topics/rest_cli_systemconfiguration.md)

