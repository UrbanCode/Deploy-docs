# deleteStatus

Delete a status

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteStatus [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|false|Type of status \(inventory, version, or snapshot\); this parameter is required you specify the name of the status instead of the ID|
|status|string|true|Name or ID of the status|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteStatus
  -type version
  -status Tested
```

Related REST command: [Delete a status](rest_cli_status_delete.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

