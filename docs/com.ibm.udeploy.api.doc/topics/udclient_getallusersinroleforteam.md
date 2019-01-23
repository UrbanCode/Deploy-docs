# getAllUsersInRoleForTeam

List all users with a given role on a team

This command returns all users in a role for a given team, including users that are associated via a group membership

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getAllUsersInRoleForTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|role|string|true|Name or id of the role|
|team|string|true|Name or id of the team|

Related REST command: [List all users with a given role on a team](rest_cli_user_inroleonteam_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

