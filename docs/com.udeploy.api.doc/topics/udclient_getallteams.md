# getAllTeams

List teams

This command lists all teams on the server, all users in each team, and all of the roles that each user has on each team.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAllTeams
```

## Parameters

None.

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getAllTeams
```

## Example response

```
[
  {
    "id": "20000000000000000000000100000000",
    "name": "System Team",
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
      }
    ],
    "applications": [],
    "environments": [],
    "processes": []
  },
  {
    "id": "e7b24877-049a-4c52-b2a1-c5c5a78895bd",
    "name": "TeamA",
    "isDeletable": true,
    "roleMappings": [
      {
        "user": {
          "id": "a459dffd-e057-494d-b119-16e85d7cd911",
          "name": "jdoe",
          "actualName": "Jane Doe",
          "displayName": "Jane Doe (jdoe)",
          "email": "jdoe@example.org",
          "deleted": false,
          "deletedDate": 0,
          "authenticationRealm": "20000000000000000000000000000001",
          "isLockedOut": false,
          "isDeletable": true
        },
        "role": {
          "id": "3b76daf9-460b-4a43-ae70-d750219c6569",
          "name": "Developer",
          "description": "",
          "isDeletable": true
        }
      },
      {
        "user": {
          "id": "7794dee7-d4c6-4f6f-b1ce-56c5d3cbfdda",
          "name": "jsmith",
          "actualName": "Joe Smith",
          "displayName": "Joe Smith (jsmith)",
          "email": "jsmith@example.org",
          "deleted": false,
          "deletedDate": 0,
          "authenticationRealm": "20000000000000000000000000000001",
          "isLockedOut": false,
          "isDeletable": true
        },
        "role": {
          "id": "3b76daf9-460b-4a43-ae70-d750219c6569",
          "name": "Developer",
          "description": "",
          "isDeletable": true
        }
      },
      {
        "user": {
          "id": "7794dee7-d4c6-4f6f-b1ce-56c5d3cbfdda",
          "name": "jsmith",
          "actualName": "Joe Smith",
          "displayName": "Joe Smith (jsmith)",
          "email": "jsmith@example.org",
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
      }
    ],
    "applications": [],
    "environments": [],
    "processes": []
  },
  {
    "id": "fe036470-0bfd-46d8-9529-11be16597435",
    "name": "TeamB",
    "isDeletable": true,
    "roleMappings": [
      {
        "user": {
          "id": "a459dffd-e057-494d-b119-16e85d7cd911",
          "name": "jdoe",
          "actualName": "Jane Doe",
          "displayName": "Jane Doe (jdoe)",
          "email": "jdoe@example.org",
          "deleted": false,
          "deletedDate": 0,
          "authenticationRealm": "20000000000000000000000000000001",
          "isLockedOut": false,
          "isDeletable": true
        },
        "role": {
          "id": "3b76daf9-460b-4a43-ae70-d750219c6569",
          "name": "Developer",
          "description": "",
          "isDeletable": true
        }
      },
      {
        "user": {
          "id": "7794dee7-d4c6-4f6f-b1ce-56c5d3cbfdda",
          "name": "jsmith",
          "actualName": "Joe Smith",
          "displayName": "Joe Smith (jsmith)",
          "email": "jsmith@example.org",
          "deleted": false,
          "deletedDate": 0,
          "authenticationRealm": "20000000000000000000000000000001",
          "isLockedOut": false,
          "isDeletable": true
        },
        "role": {
          "id": "3b76daf9-460b-4a43-ae70-d750219c6569",
          "name": "Developer",
          "description": "",
          "isDeletable": true
        }
      },
      {
        "user": {
          "id": "a459dffd-e057-494d-b119-16e85d7cd911",
          "name": "jdoe",
          "actualName": "Jane Doe",
          "displayName": "Jane Doe (jdoe)",
          "email": "jdoe@example.org",
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
      }
    ],
    "applications": [],
    "environments": [],
    "processes": []
  }
]

```

Related REST command: [List teams](rest_cli_team_infoall_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

