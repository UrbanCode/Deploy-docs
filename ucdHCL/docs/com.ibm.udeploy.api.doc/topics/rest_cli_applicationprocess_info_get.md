# Get information about an application process

Returns a JSON representation of an application process.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcess/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|applicationProcess|string|true|Name of the process|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "b02d0960-e878-45b5-88d9-7461159f0e19",
  "name": "Deploy JPetStore",
  "description": "",
  "active": true,
  "inventoryManagementType": "AUTOMATIC",
  "offlineAgentHandling": "PRE_EXECUTION_CHECK",
  "versionCount": 2,
  "version": 2,
  "commit": 30,
  "path": "applications/c8a45972-da39-4450-87f0-21fae710e0f5/processes/b02d0960-e878-45b5-88d9-7461159f0e19"
}
```

Related CLI command: [getApplicationProcess](udclient_getapplicationprocess.md).

**Parent topic:** [applicationProcess resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_applicationprocess.md)

