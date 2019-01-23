# Get information about a component process

This command returns a JSON representation of a component process.

## Request

```
GET https://{hostname}:{port}
    /cli/componentProcess/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|componentProcess|string|true|Name or ID of the component process|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "c59721d1-a02c-4b3f-9eb7-bde5358210d0",
  "name": "Deploy application component",
  "description": "",
  "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
  "takesVersion": true,
  "inventoryActionType": "ADD",
  "status": "Active",
  "configActionType": "ADD",
  "active": true,
  "versionCount": 4,
  "version": 4,
  "commit": 32,
  "path": "components/69a6a5bd-583b-4b40-bd47-54b28f5aa1e6/processes/c59721d1-a02c-4b3f-9eb7-bde5358210d0"
}
```

Related CLI command: [getComponentProcess](udclient_getcomponentprocess.md).

**Parent topic:** [componentProcess resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_componentprocess.md)

