# Remove a link from a version

## Request

```
DELETE https://{hostname}:{port}
    /cli/version/removeLink?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|linkName|string|true|Name of the link to remove|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [removeVersionLink](udclient_removeversionlink.md).

**Parent topic:** [version resource](../../com.udeploy.api.doc/topics/rest_cli_version.md)

