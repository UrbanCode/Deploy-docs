# addUserToGroup

Add a user to a group

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addUserToGroup [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|
|group|string|true|Name of the group|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addUserToGroup 
  -user jsmith
  -group group1
```

Related REST command: [Add a user to a group](rest_cli_group_adduser_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

