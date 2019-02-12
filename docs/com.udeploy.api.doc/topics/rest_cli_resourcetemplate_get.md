# Get a resource template

## Request

```
GET https://{hostname}:{port}
    /cli/resourceTemplate?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|template|string|true|Name or ID of resource template|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  resourceTemplate?template=MyResourceTemplate" 

```

## Example response

```
{
  "propDefs": [],
  "security": {
    "read": true,
    "Create Resource Templates": true,
    "Delete": true,
    "Edit Basic Settings": true,
    "Manage Resources": true,
    "Manage Teams": true,
    "View Resource Templates": true
  },
  "propSheetDef": {
    "id": "27c709ec-07d8-49b2-bf20-639b07e625d5",
    "versioned": false,
    "resolveHttpValuesUrl": "property/propSheetDef/27c709ec-07d8-49b2-bf20-639b07e625d5/resolveHttpValues"
  },
  "propSheet": {
    "id": "4d0b0d8c-8405-44de-a8a9-4fe7ffb36c19",
    "versioned": false
  },
  "extendedSecurity": {
    "read": true,
    "Create Resource Templates": true,
    "Delete": true,
    "Edit Basic Settings": true,
    "Manage Resources": true,
    "Manage Teams": true,
    "View Resource Templates": true,
    "teams": []
  },
  "id": "95583b93-13e3-484c-b444-480008e5083d",
  "securityResourceId": "ed438378-f215-4fd0-92d0-1cfcce26e621",
  "name": "MyResourceTemplate",
  "description": "",
  "deleted": false
}

```

Related CLI command: [getResourceTemplate](udclient_getresourcetemplate.md).

**Parent topic:** [resourceTemplate resource](../../com.udeploy.api.doc/topics/rest_cli_resourcetemplate.md)

