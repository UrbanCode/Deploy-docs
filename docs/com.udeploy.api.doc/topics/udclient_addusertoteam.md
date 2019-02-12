# addUserToTeam

Add a user to a team

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addUserToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|
|team|string|true|Name of the team|
|role|string|true|Name of the role to give to the user|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addUserToTeam
  -user jdoe
  -team MyTeam
  -role MyRole
```

Related REST command: [Add a user to a team](rest_cli_teamsecurity_users_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

