# Delete a team

## Request

```
PUT https://{hostname}:{port}
    /cli/team/delete?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/team/delete
  ?team=MyNewTeam" -X PUT
```

Related CLI command: [deleteTeam](udclient_deleteteam.md).

**Parent topic:** [team resource](../../com.udeploy.api.doc/topics/rest_cli_team.md)

