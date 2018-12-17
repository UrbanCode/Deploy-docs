# Add a user to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/teamsecurity/users?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|
|team|string|true|Name of the team|
|role|string|true|Name of the role to give to the user|

Related CLI command: [addUserToTeam](udclient_addusertoteam.md).

**Parent topic:** [teamsecurity resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_teamsecurity.md)

