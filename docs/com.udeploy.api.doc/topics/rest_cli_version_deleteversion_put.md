# Delete a version from a component

## Request

```
PUT https://{hostname}:{port}
    /cli/version/deleteVersion?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component|
|version|string|true|Name or ID of the version\(s\) to be deleted. This option can be repeated to delete multiple versions.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/deleteVersion
  ?component=MyComponent&version=1.0" -X PUT
```

Related CLI command: [deleteVersion](udclient_deleteversion.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

