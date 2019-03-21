# getAllLatestDesiredInventory

Get all of the latest desired inventory for an environment.

This command returns a JSON array of all of the desired inventory for an environment. It optionally groups the desired inventory by component.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAllLatestDesiredInventory
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|Name or ID of the environment|
|groupVersions|boolean|true|True if the versions should be grouped by component.|

Related REST command: [Get all of the latest desired inventory for an environment.](rest_cli_envid_latestdesiredinventory_groupversions_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

