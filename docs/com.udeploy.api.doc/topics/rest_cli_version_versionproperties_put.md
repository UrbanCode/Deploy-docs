# Set a property on a component version

## Request

```
PUT https://{hostname}:{port}
    /cli/version/versionProperties
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Name or ID of the component; this value is 
  required if you specify the version name instead of ID",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)",
  "version": "Name or ID of the version"
}

```

## Example response

```
{
  "id": "33528ab5-a7be-46cb-9f0c-916a42bd2f62",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related CLI command: [setVersionProperty](udclient_setversionproperty.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

