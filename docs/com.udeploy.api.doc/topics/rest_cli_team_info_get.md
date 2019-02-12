# List information about a team

## Request

```
GET https://{hostname}:{port}
    /cli/team/info?{parameters}
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
   
  "https://myserver.example.com:8443/cli/team/info
  ?team=MyNewTeam" -X GET -H "Accept: application/json"
```

## Example response

```
{
  "id": "769c2486-ed40-4a3a-ac52-faa33d30cfd5",
  "name": "MyNewTeam",
  "isDeletable": true,
  "roleMappings": [
    {
      "user": {
        "id": "20000000000000000000000001000000",
        "name": "admin",
        "displayName": "admin",
        "deleted": false,
        "deletedDate": 0,
        "authenticationRealm": "20000000000000000000000000000001",
        "isLockedOut": false,
        "isDeletable": true
      },
      "role": {
        "id": "20000000000000000000000000010001",
        "name": "Administrator",
        "description": "",
        "isDeletable": true
      }
    },
    {
      "user": {
        "id": "2d2c8241-ba69-4b63-abf0-de90b7d4ceeb",
        "name": "jdoe",
        "actualName": "Jane Doe",
        "displayName": "Jane Doe (jdoe)",
        "email": "",
        "deleted": false,
        "deletedDate": 0,
        "authenticationRealm": "20000000000000000000000000000001",
        "isLockedOut": false,
        "isDeletable": true
      },
      "role": {
        "id": "90f5f9a0-3d01-4aaa-a276-74214188fd1d",
        "name": "Developer",
        "isDeletable": true
      }
    },
    {
      "user": {
        "id": "b1e20a57-2897-4372-b6c6-662c719e6dda",
        "name": "jsmith",
        "actualName": "Joe Smith",
        "displayName": "Joe Smith (jsmith)",
        "email": "",
        "deleted": false,
        "deletedDate": 0,
        "authenticationRealm": "20000000000000000000000000000001",
        "isLockedOut": false,
        "isDeletable": true
      },
      "role": {
        "id": "e407437d-0c5f-446f-939f-9fa4d7df4d5e",
        "name": "Observer",
        "isDeletable": true
      }
    }
  ]
}

```

Related CLI command: [getTeam](udclient_getteam.md).

**Parent topic:** [team resource](../../com.udeploy.api.doc/topics/rest_cli_team.md)

