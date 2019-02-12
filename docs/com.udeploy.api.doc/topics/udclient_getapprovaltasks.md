# getApprovalTasks

List recent approval tasks

This command returns the approval tasks that have been modified since the given time.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApprovalTasks [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|modifiedAfter|long|false|Include approval tasks that have been created or edited since this provided time. \(Optional\)|

Related REST command: [List recent approval tasks](rest_cli_approval_task__get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

