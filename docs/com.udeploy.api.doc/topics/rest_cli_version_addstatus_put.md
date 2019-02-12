# Add a status to a version

## Request

```
PUT https://{hostname}:{port}
    /cli/version/addStatus?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|status|string|true|Name of the status to apply|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [addVersionStatus](udclient_addversionstatus.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

