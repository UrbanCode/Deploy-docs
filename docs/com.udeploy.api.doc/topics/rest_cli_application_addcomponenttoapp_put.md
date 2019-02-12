# Add a component to an application.

## Request

```
PUT https://{hostname}:{port}
    /cli/application/addComponentToApp?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name of the component|
|application|string|true|Name of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application/addComponentToApp
  ?component=MyComponent&application=MyApplication" -X PUT
```

Related CLI command: [addComponentToApplication](udclient_addcomponenttoapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

