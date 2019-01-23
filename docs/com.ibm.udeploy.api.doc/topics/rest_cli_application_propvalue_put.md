# Set a property on an application

## Request

```
PUT https://{hostname}:{port}
    /cli/application/propValue
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Property name",
  "value": "Property value (optional)"
}

```

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application/propValue
  ?application=JPetStore&name=Prop4&value=value4" -X PUT
```

## Example response

```
{
  "id": "7b818dfe-efd9-465a-bee3-775f60dc297d",
  "name": "Prop4",
  "value": "value4",
  "secure": false
}
```

Related CLI command: [setApplicationProperty](udclient_setapplicationproperty.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

