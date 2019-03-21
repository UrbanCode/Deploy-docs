# Create a resource template from a JSON file

This method supports importing a resource template from a cloud system.

## Request

```
PUT https://{hostname}:{port}
    /cli/resourceTemplate/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "cloudResourceId": "ID of cloud resource; leave blank 
  when not cloud-based template (Optional)",
  "connection": "ID of cloud connection; leave blank when 
  not cloud-based template (Optional)",
  "description": "Description",
  "isVsys": "Specify 'true' when cloud resource is Virtual 
  System Pattern (non-classic) in IPAS 2.0 or ICO 2.0 cloud 
  product, otherwise specify 'false' when cloud resource is 
  using Weaver (for IWD, SCO, ICO, and IPAS versions before 
  2.0 and 'classic' virtual system pattern in IPAS 2.0 or 
  ICO 2.0); leave blank when not cloud-based template 
  (Optional)",
  "name": "Name for the resource template",
  "parentId": "ID of parent resource template; leave blank 
  when none or creating cloud-based template (Optional)",
  "rootTeamMappings": "Array of UCD team ids; if not 
  specified, no teams will be mapped to Root Resource; 
  format: [ {teamId: 'ID-of-team-1'}, {teamId: 'ID-of-team-
  2'}, ... ]; (Optional)",
  "teamMappings": "Array of UCD team ids; if not 
  specified, no teams will be mapped to Template; format: [ 
  {teamId: 'ID-of-team-1'}, {teamId: 'ID-of-team-2'}, ... ]; 
  (Optional)"
}

```

Related CLI command: [createResourceTemplate](udclient_createresourcetemplate.md).

**Parent topic:** [resourceTemplate resource](../../com.udeploy.api.doc/topics/rest_cli_resourcetemplate.md)

