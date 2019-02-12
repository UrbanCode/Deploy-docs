# deleteGroup

Delete a group

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  deleteGroup [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  deleteGroup 
  -group group1
```

Related REST command: [Delete a group](rest_cli_group_delete_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

