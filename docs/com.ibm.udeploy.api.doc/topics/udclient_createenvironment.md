# createEnvironment

Create a new environment

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createEnvironment [parameters] [JSON file]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|false|Application to add the environment to|
|name|string|false|Name of the new environment|
|description|string|false|Description of the new environment|
|color|string|false|Color of the new environment, in hex format. For a REST call, URL encode the \# symbol; for example, %23ff0000 for pure red. For a udclient command, put the color in hex format in quotes; for example '\#ff0000'.|
|requireApprovals|boolean|false|Whether the environment requires approvals|
|noSelfApprovals|boolean|false|Whether the environment allows self approvals|

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "applicationId": "Application ID associated with the 
  Environment template.",
  "description": "Description (optional)",
  "name": "Environment name",
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
  createEnvironment 
  -application JPetStore 
  -name NewEnvironment
  -color '#ff0000'
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

**Note:** 

The createEnvironment can now take a JSON input string like createApplication and createComponent. You can still pass in query parameters \(udclient createEnvironment -name "name"\) OR you can specify a JSON file with configuration \(udclient createEnvironment env.json\). The method will throw an exception if it specifies query parameters and a JSON configuration file.

The configuration file template should look like:

```
{
"name": "Environment Name",
"description": "Description (optional)",
"applicationId", "Application ID associated with EnvironmentTemplate",
"teamMappings": (detailed above)
}
```

Related REST command: [Create a new environment](rest_cli_environment_createenvironment_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

