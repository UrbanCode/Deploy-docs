# createApplication

Create an application from a JSON file

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createApplication [JSON file]
```

## Parameters

None.

## Template

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

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createApplication newApplication.json
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

## Team mappings

When creating UrbanCode Deploy objects from the CLI we pass in JSON payloads that set the configuration.

These JSON files can include a "teamMappings" attribute that looks like this:

```
"teamMapping":[ 
{ 
"teamId" : "TEAM UIID", "teamLabel": "TEAM NAME", (can specify teamId or teamLabel), 
"resourceRoleId": "ResRole UUID", "resourceRoleLabel":"Name of Resource Role" (can specify this or resRoleId) }
,
{ "teamId" : "TEAM UIID2", "teamLabel": "TEAM NAME2", (can specify teamId or teamLabel), 
"resourceRoleId": "ResRole UUID2", "resourceRoleLabel":"Name of Resource Role2" (can specify this or resRoleId) }
,
{MORE TEAM MAPPINGS}
]
```

Related REST command: [Create an application from a JSON file](rest_cli_application_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

