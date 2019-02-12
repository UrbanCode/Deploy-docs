# Delete all redundant versions for a component in an environment

A version is considered redundant if all of its files have been replaced by versions that have been deployed more recently to the same environment.

## Request

```
DELETE https://{hostname}:{port}
    /cli/environment/{environmentId}/redundantVersions/{componentId}?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|deleteRedundant|boolean|false|If set to true, redundant versions will be removed from the environment's inventory.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true| |
|componentId|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [deleteRedundantDesiredInventoryVersions](udclient_deleteredundantdesiredinventoryversions.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

