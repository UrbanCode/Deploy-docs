# Delete all versions for a component in an environment

## Request

```
DELETE https://{hostname}:{port}
    /cli/environment/{environmentId}/versions/{componentId}?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|deleteVersions|boolean|false|If set to true, versions will be removed from the environment's inventory.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true| |
|componentId|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [deleteAllDesiredInventoryVersions](udclient_deletealldesiredinventoryversions.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

