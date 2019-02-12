# Get a version ID

## Request

```
GET https://{hostname}:{port}
    /cli/version/getVersionId?{parameters}
Accept: text/plain

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`text/plain`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/getVersionId?
  component=MyComponent&version=1.2"
```

## Example response

```
1a53a4a6-bfcd-4014-a0ab-83f97077a4d4
```

Related CLI command: [getVersionId](udclient_getversionid.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

