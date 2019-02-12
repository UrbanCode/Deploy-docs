# Update a team

Specify the team name in the 'team' parameter and use the 'name' and 'description' parameters to specify the desired changes.

## Request

```
PUT https://{hostname}:{port}
    /cli/team/update?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team to be changed|
|name|string|false|New name of the team|
|description|string|false|New description of the team|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/team/create
  ?team=MyNewTeam&name=ADifferentTeamName&description=ADifferentTeamDescription" 
  -X PUT
```

Related CLI command: [updateTeam](udclient_updateteam.md).

**Parent topic:** [team resource](../../com.udeploy.api.doc/topics/rest_cli_team.md)

