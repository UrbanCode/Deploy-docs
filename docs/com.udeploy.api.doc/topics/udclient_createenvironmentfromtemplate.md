# createEnvironmentFromTemplate

Create a new environment from template

This command creates and Environment from a template and attaches it to the specified application.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createEnvironmentFromTemplate [JSON file]
```

## Parameters

None.

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
  }],
  "templateId": "ID of the template to use, either this 
  field or templateName are required.",
  "templateName": "Name of a template to use, either this 
  field or templateId are required."
}

```

Related REST command: [Create a new environment from template](rest_cli_environment_createenvironmentfromtemplate_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

