# Remove a status from a version

## Request

```
DELETE https://{hostname}:{port}
    /cli/version/status?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Nameor ID of the version|
|status|string|true|Name of the status to apply|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [removeVersionStatus](udclient_removeversionstatus.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

