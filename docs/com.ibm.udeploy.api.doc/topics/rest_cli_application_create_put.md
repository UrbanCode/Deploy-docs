# Create an application from a JSON file

## Request

```
PUT https://{hostname}:{port}
    /cli/application/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "description": "Description",
  "enforceCompleteSnapshots": "Specify true to require an 
  explicit version for each component",
  "name": "Application name or ID",
  "notificationScheme": "Notification scheme",
  "teamMappings": [{
    "resourceRoleId": "Id of Resource Type to apply to 
  this team mapping (optional, can specify either this or 
  resourceRoleLabel",
    "resourceRoleLabel": "Name of Resource Type to apply 
  to this team mapping (optional, can specify either this or 
  resourceRoleId",
    "teamId": "ID of a team, either this field or 
  teamLabel are needed to specify a team",
    "teamLabel": "Name of the team to map the environment 
  to, either this field or teamId are needed to specify a 
  team"
  }]
}

```

## Example JSON request

```
{
  "name": "My new application",
  "description": "New application for command example",
  "notificationScheme": "Default Notification Scheme",
  "enforceCompleteSnapshots": "false"
}
```

## Example response

```
{
  "id": "5064e2b5-08aa-4e79-b0d5-9b63ba218d48",
  "name": "My new application",
  "description": "New application for command example",
  "created": 1390504790883,
  "enforceCompleteSnapshots": false,
  "active": true,
  "tags": [
  ],
  "user": "admin"
}
```

Related CLI command: [createApplication](udclient_createapplication.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

