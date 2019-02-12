# Create a new environment from template

This command creates and Environment from a template and attaches it to the specified application.

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/createEnvironmentFromTemplate
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

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

Related CLI command: [createEnvironmentFromTemplate](udclient_createenvironmentfromtemplate.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

