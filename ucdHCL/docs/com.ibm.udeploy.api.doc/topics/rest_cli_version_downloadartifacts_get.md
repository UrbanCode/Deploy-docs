# Download the artifacts of a component version

This command exports the artifacts of a component version into an archive file.

## Request

```
GET https://{hostname}:{port}
    /cli/version/downloadArtifacts?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|location|string|true|Path to download the artifacts to. You must have permission to create files in this location.|
|singleFilePath|string|false|Optional path to an individual version artifact to download. If specified, only that file will be downloaded.|
|encoding|string|false|Optional character encoding to determine the file names of the artifacts. Defaults to the encoding of the file system.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/version/downloadArtifacts
  ?component=JPetStore-WEB&version=1.0"
```

Related CLI command: [downloadVersionArtifacts](udclient_downloadversionartifacts.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

