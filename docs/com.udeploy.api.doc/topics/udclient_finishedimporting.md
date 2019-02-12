# finishedImporting

Mark a version as completed importing

Mark a version as completed importing so it is available for use in deployments

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  finishedImporting [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|version|string|true|Name or id of version|
|component|string|false|Name or id of the component. This is required if version name is used|

Related REST command: [Mark a version as completed importing](rest_cli_version_finishedimporting_post.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

