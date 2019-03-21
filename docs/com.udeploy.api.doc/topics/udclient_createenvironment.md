# createEnvironment

Create a new environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
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
  "cleanupCountToKeep": "Number of most recently deployed 
  versions to keep (optional)",
  "cleanupDaysToKeep": "Number of days to keep versions 
  deployed to this environment (optional)",
  "color": "HTML color code for the environment (optional)",
  "description": "Description (optional)",
  "historyCleanupDaysToKeep": "Number of days to keep 
  application process history for this environment 
  (optional)",
  "lockSnapshots": "Whether snapshots will be locked when 
  deployed to this environment (optional)",
  "name": "Environment name",
  "noSelfApprovals": "When this option is selected, users 
  that submit deployment requests cannot approve their own 
  requests (optional)",
  "requireApprovals": "Whether approvals will be required 
  (optional)",
  "requireSnapshot": "If enabled, all deployments must use 
  a snapshot instead of loose versions (optional)",
  "snapshotDaysToKeep": "Number of days to keep snapshots 
  deployed to this environment (optional)",
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
  }],
  "useSystemDefaultDays": "Whether or not to use the 
  system default number of days to keep application process 
  history for this environment (optional)"
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

Related REST command: [Create a new environment](rest_cli_environment_createenvironment_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

