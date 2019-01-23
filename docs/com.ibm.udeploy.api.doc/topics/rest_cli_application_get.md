# Get information about all applications on the server

This command returns a JSON representation of all applications.

## Request

```
GET https://{hostname}:{port}
    /cli/application
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application
  ?active=true"
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

Related CLI command: [getApplications](udclient_getapplications.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

