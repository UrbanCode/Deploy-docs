# Get information about a component

This command returns a JSON representation of a component.

## Request

```
GET https://{hostname}:{port}
    /cli/component/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/component/info
  ?component=JPetStore-APP"
```

## Example response

```
{
  "id": "69a6a5bd-583b-4b40-bd47-54b28f5aa1e6",
  "name": "JPetStore-APP",
  "description": "",
  "created": 1387315824908,
  "importAutomatically": false,
  "useVfs": true,
  "active": true,
  "deleted": false,
  "defaultVersionType": "FULL",
  "cleanupDaysToKeep": 0,
  "cleanupCountToKeep": 0,
  "tags": [
    {
      "id": "d140ae5a-dfb0-477a-910b-762cc0d99cc6",
      "name": "Tag2",
      "color": "#7fff00",
      "description": "",
      "objectType": "Component"
    }
  ],
  "user": "admin",
  "properties": [
    {
      "id": "91b61a4a-1454-46d9-af32-eb98e6ae7d3d",
      "name": "code_station/repository",
      "value": "9f19c4c5-84b9-4f4e-b1fc-df2c2f306b1c",
      "description": "",
      "secure": false
    },
    {
      "id": "3702f391-09e1-4550-903a-d5ae286c94aa",
      "name": "custom/Prop1",
      "value": "value1",
      "description": "",
      "secure": false
    },
    {
      "id": "4fcb6120-453d-45a5-8cb3-9e7945dc80a5",
      "name": "FileSystemVersionedComponentProperties/basePath",
      "value": "/root/shared/app",
      "description": "",
      "secure": false
    },
    {
      "id": "8f3706d1-8255-4626-b349-6e503a1ed4e4",
      "name": "FileSystemVersionedComponentProperties/extensions",
      "value": "",
      "description": "",
      "secure": false
    },
    {
      "id": "8bba5e9f-7937-4b24-ac12-ebd6250f0023",
      "name": "FileSystemVersionedComponentProperties/saveFileExecuteBits",
      "value": "false",
      "description": "",
      "secure": false
    }
  ],
  "applications": [
    {
      "id": "c8a45972-da39-4450-87f0-21fae710e0f5",
      "name": "JPetStore",
      "description": "",
      "created": 1387378155981,
      "enforceCompleteSnapshots": false,
      "active": true,
      "tags": [
      ],
      "user": "admin"
    }
  ],
  "environmentPropSheetDef": {
    "id": "8f9bf513-d434-43d4-ada4-6b8d16cfe4c2",
    "path": "components/69a6a5bd-583b-4b40-bd47-54b28f5aa1e6/environmentPropSheetDef",
    "version": 1,
    "versionCount": 1,
    "commit": 6,
    "versioned": true
  },
  "versionPropSheetDef": {
    "id": "99bb8cce-44ee-49df-bebc-e84dbbdba2ac",
    "path": "components/69a6a5bd-583b-4b40-bd47-54b28f5aa1e6/versionPropSheetDef",
    "version": 1,
    "versionCount": 1,
    "commit": 6,
    "versioned": true
  },
  "propSheet": {
    "id": "cb6049f9-bcce-4806-9d24-de5d729f40b3",
    "name": "custom",
    "path": "components/69a6a5bd-583b-4b40-bd47-54b28f5aa1e6/propSheetGroup/propSheets/cb6049f9-bcce-4806-9d24-de5d729f40b3",
    "version": 2,
    "versionCount": 2,
    "commit": 87,
    "versioned": true
  },
  "templatePropSheet": {
    "id": "e94a21c9-138c-4c36-91a0-ddc9d6f5cf07",
    "name": "template",
    "path": "components/69a6a5bd-583b-4b40-bd47-54b28f5aa1e6/propSheetGroup/propSheets/e94a21c9-138c-4c36-91a0-ddc9d6f5cf07",
    "version": 1,
    "versionCount": 1,
    "commit": 6,
    "versioned": true
  },
  "resourceRole": {
    "id": "06c00bb6-5ff0-4960-867f-5fb8d2e69222",
    "name": "JPetStore-APP",
    "specialType": "COMPONENT",
    "propSheetDef": {
      "id": "100de7fc-182f-4fcf-8299-46fae5a06935",
      "name": "JPetStore-APP",
      "versioned": false
    },
    "propDefs": [
      {
        "id": "bb8404e1-c030-436e-ba2f-c2616216cf18",
        "name": "myProp",
        "label": "myProp",
        "pattern": "",
        "type": "TEXT",
        "value": "42",
        "required": false,
        "description": ""
      }
    ]
  },
  "systemCleanupDaysToKeep": -1,
  "systemCleanupCountToKeep": -1,
  "extendedSecurity": {
    "read": true,
    "write": true,
    "Create Components": true,
    "Edit Components": true,
    "Manage Versions": true,
    "View Components": true,
    "teams": [
    ]
  }
```

Related CLI command: [getComponent](udclient_getcomponent.md).

**Parent topic:** [component resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_component.md)

