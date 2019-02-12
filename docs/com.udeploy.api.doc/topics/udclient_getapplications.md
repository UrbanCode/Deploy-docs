# getApplications

Get information about all applications on the server

This command returns a JSON representation of all applications.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplications
```

## Parameters

None.

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplications
```

## Example response

```
[
  {
    "id": "c8a45972-da39-4450-87f0-21fae710e0f5",
    "name": "JPetStore",
    "description": "",
    "created": 1387378155981,
    "enforceCompleteSnapshots": false,
    "active": true,
    "tags": [
    ],
    "user": "admin"
  },
  {
    "id": "b0d47a25-c90e-4286-8b9e-6a08a1da45bc",
    "name": "My Application",
    "description": "",
    "created": 1390502070483,
    "enforceCompleteSnapshots": false,
    "active": true,
    "tags": [
    ],
    "user": "admin"
  }
]
```

Related REST command: [Get information about all applications on the server](rest_cli_application_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

