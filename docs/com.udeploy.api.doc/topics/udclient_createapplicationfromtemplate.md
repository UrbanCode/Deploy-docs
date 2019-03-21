# createApplicationFromTemplate

Create an application with components from a JSON file

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createApplicationFromTemplate [JSON file]
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
  "existingComponentIds": "The list of existing Component 
  IDs to attach the application.",
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
  }],
  "templateId": "The ID of the template to use. If you are 
  using an application template, either this field or 
  templateName are required.",
  "templateName": "The name of the template to use. If you 
  are using an application template, either this field or 
  templateId are required.",
  "templateVersion": "The version of the template to use. 
  This field is required if you are using an application 
  template."
}

```

Related REST command: [Create an application with components from a JSON file](rest_cli_application_createapplicationfromtemplate_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

