# deleteRedundantDesiredInventoryVersions

Delete all redundant versions for a component in an environment

A version is considered redundant if all of its files have been replaced by versions that have been deployed more recently to the same environment.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteRedundantDesiredInventoryVersions [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|deleteRedundant|boolean|false|If set to true, redundant versions will be removed from the environment's inventory.|
|environmentId|string|true| |
|componentId|string|true|Name or ID of the component|

Related REST command: [Delete all redundant versions for a component in an environment](rest_cli_envid_redundantversions_componentid_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

