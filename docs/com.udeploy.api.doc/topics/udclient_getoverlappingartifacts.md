# getOverlappingArtifacts

Get all artifacts overlapped in the given version

Get all artifacts that are overlapped by later versions. A version is considered safe to rollback if it does not contain overlapping artifacts. It is risky to roll back a version if that version contains overlapping artifacts. This command applies only to z/OS component versions.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getOverlappingArtifacts
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resourceId|string|true|Name or ID of the resource|
|versionId|string|true|Name or ID of the version to check risky status|
|environmentId|string|true|Name or ID of the environment|
|componentId|string|true|Name or ID of the component|

Related REST command: [Get all artifacts overlapped in the given version](rest_cli_envid_componentid_resourceid_overlappingartifacts_versionid_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

