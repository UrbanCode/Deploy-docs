# Get all artifacts overlapped in the given version

Get all artifacts that are overlapped by later versions. A version is considered safe to rollback if it does not contain overlapping artifacts. It is risky to roll back a version if that version contains overlapping artifacts. This command applies only to z/OS component versions.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/{environmentId}/{componentId}/{resourceId}/overlappingArtifacts/{versionId}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resourceId|string|true|Name or ID of the resource|
|versionId|string|true|Name or ID of the version to check risky status|
|environmentId|string|true|Name or ID of the environment|
|componentId|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getOverlappingArtifacts](udclient_getoverlappingartifacts.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

