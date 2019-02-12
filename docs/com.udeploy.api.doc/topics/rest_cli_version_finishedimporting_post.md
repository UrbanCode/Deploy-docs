# Mark a version as completed importing

Mark a version as completed importing so it is available for use in deployments

## Request

```
POST https://{hostname}:{port}
    /cli/version/finishedImporting?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|version|string|true|Name or id of version|
|component|string|false|Name or id of the component. This is required if version name is used|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [finishedImporting](udclient_finishedimporting.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

