# getApplication

Get information about an application

This command returns a JSON representation of an application.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplication 
  -application JPetStore
```

## Example response

```
{
  "id": "c8a45972-da39-4450-87f0-21fae710e0f5",
  "name": "JPetStore",
  "description": "",
  "created": 1387378155981,
  "enforceCompleteSnapshots": false,
  "active": true,
  "tags": [
  ],
  "user": "admin",
  "componentCount": 3,
  "extendedSecurity": {
    "read": true,
    "write": true,
    "Create Applications": true,
    "Edit Applications": true,
    "Manage Snapshots": true,
    "Run Component Processes": true,
    "View Applications": true,
    "teams": [
    ]
  }
}
```

Related REST command: [Get information about an application](rest_cli_application_info_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

