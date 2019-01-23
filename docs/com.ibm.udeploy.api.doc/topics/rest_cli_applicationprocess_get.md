# Get all application processes of an application

Returns a JSON representation of all application processes for a specific application.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcess?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [getAllApplicationProcessesForApplication](udclient_getallapplicationprocessesforapplication.md).

**Parent topic:** [applicationProcess resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_applicationprocess.md)

