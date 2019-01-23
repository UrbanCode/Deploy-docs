# Create a component version

Do not use the keywords latest, latestVersion, or newest as the version name.

## Request

```
POST https://{hostname}:{port}
    /cli/version/createVersion?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|name|string|true|Name of the new version|
|description|string|false|Description of the new version|
|type|string|false|Type to use for the new version \(incremental or full\) - full is the default.|
|sourceConfigExecutionRecordId|string|false|A system parameter. This should not be provided by the user or by user scripts.|
|importing|boolean|false|Whether or not to mark this version as importing. Version marked as importing cannot be used in deployments. Default false|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "c0198aaf-6f4b-4d2e-b103-a7f6a257f580",
  "name": "1.2",
  "type": "FULL",
  "created": 1390572847946,
  "active": true,
  "archived": false
}
```

Related CLI command: [createVersion](udclient_createversion.md).

**Parent topic:** [version resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_version.md)

