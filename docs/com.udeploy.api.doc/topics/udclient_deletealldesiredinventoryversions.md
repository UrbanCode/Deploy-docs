# deleteAllDesiredInventoryVersions

Delete all versions for a component in an environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteAllDesiredInventoryVersions [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|deleteVersions|boolean|false|If set to true, versions will be removed from the environment's inventory.|
|environmentId|string|true| |
|componentId|string|true|Name or ID of the component|

Related REST command: [Delete all versions for a component in an environment](rest_cli_envid_versions_componentid_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

