# addGroupToTeam

Add a group to a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addGroupToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|
|team|string|true|Name of the team|
|role|string|true|Name of the role to give to the group|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addGroupToTeam
  -group group1
  -team MyTeam
  -role MyRole
```

Related REST command: [Add a group to a team](rest_cli_teamsecurity_groups_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

