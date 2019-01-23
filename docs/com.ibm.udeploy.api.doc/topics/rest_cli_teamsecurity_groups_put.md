# Add a group to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/teamsecurity/groups?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|
|team|string|true|Name of the team|
|role|string|true|Name of the role to give to the group|

Related CLI command: [addGroupToTeam](udclient_addgrouptoteam.md).

**Parent topic:** [teamsecurity resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_teamsecurity.md)

