# Update a resource template from a JSON file

To update a resource template with this command, you must specify all of the existing data for the resource template as defined in the JSON data template, except 'teamMappings' which is optional.

## Request

```
PUT https://{hostname}:{port}
    /cli/resourceTemplate/update
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "description": "Description",
  "existingId": "ID of resource template; leave blank when 
  creating new template",
  "name": "Name for the resource template",
  "rootTeamMappings": "Array of UCD team ids; if not 
  specified, no teams will be mapped to Root Resource; 
  format: [ {teamId: '<ID-of-team-1>'}, {teamId: '<ID-of-
  team-2>'}, ... ]; (Optional)",
  "teamMappings": "Array of UCD team ids; if not 
  specified, no teams will be mapped to Template; format: [ 
  {teamId: '<ID-of-team-1>'}, {teamId: '<ID-of-team-2>'}, 
  ... ]; (Optional)"
}

```

Related CLI command: [updateResourceTemplate](udclient_updateresourcetemplate.md).

**Parent topic:** [resourceTemplate resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resourcetemplate.md)

