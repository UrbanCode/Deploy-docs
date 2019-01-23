# Create a team

## Request

```
PUT https://{hostname}:{port}
    /cli/team/create?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|team|string|true|Name of the team|
|description|string|false|Description of the team|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/team/create
  ?team=MyNewTeam&description=MyNewTeamDescription" -X PUT -H "Accept: application/json"
```

## Example response

```
{
  "id": "769c2486-ed40-4a3a-ac52-faa33d30cfd5",
  "name": "MyNewTeam",
  "description": "MyNewTeamDescription",
  "isDeletable": true
}

```

Related CLI command: [createTeam](udclient_createteam.md).

**Parent topic:** [team resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_team.md)

