# Get information about an application

This command returns a JSON representation of an application.

## Request

```
GET https://{hostname}:{port}
    /cli/application/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
  
  "https://myserver.example.com:8443/cli/application/info
  ?application=JPetStore"
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

Related CLI command: [getApplication](udclient_getapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

