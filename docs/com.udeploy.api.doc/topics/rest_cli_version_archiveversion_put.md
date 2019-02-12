# Archive the given versions of a component

## Request

```
PUT https://{hostname}:{port}
    /cli/version/archiveVersion?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|version|string|true|Name or ID of the version\(s\) to be archived. This option can be repeated to archive multiple versions.|
|path|string|false|Archive path. An absolute path which overrides the System's archive path|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/archiveVersion
  ?component=MyComponent&version=1.0&version=1.2&version=1.3" -X PUT
```

Related CLI command: [archiveVersion](udclient_archiveversion.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

