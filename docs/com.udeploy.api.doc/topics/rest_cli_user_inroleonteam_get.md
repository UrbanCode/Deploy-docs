# List all users with a given role on a team

This command returns all users in a role for a given team, including users that are associated via a group membership

## Request

```
GET https://{hostname}:{port}
    /cli/user/inRoleOnTeam?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|role|string|true|Name or id of the role|
|team|string|true|Name or id of the team|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getAllUsersInRoleForTeam](udclient_getallusersinroleforteam.md).

**Parent topic:** [user resource](../../com.udeploy.api.doc/topics/rest_cli_user.md)

