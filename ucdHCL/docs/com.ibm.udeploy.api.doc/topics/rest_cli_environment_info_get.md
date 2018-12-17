# Get information about an environment

This command returns a JSON representation of an environment.

## Request

```
GET https://{hostname}:{port}
    /cli/environment/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "1f97af86-cde3-4ba2-803b-0e4580dcc05b",
  "name": "Tutorial environment 1",
  "description": "",
  "color": "#ffffff",
  "requireApprovals": false,
  "lockSnapshots": false,
  "calendarId": "e237199e-8bbc-497e-97eb-ca2568dff91c",
  "active": true,
  "cleanupDaysToKeep": 0,
  "cleanupCountToKeep": 0,
  "conditions": [
  ],
  "compliancy": {
    "missingCount": 0,
    "correctCount": 3,
    "desiredCount": 3
  },
  "systemCleanupDaysToKeep": -1,
  "systemCleanupCountToKeep": -1,
  "exemptProcesses": "",
  "extendedSecurity": {
    "read": true,
    "write": true,
    "execute": true,
    "Create Environments": true,
    "Edit Environments": true,
    "Execute on Environments": true,
    "View Environments": true,
    "teams": [
      {
        "teamId": "ea307e2e-d6be-4092-a7e8-e8e02274de7e",
        "teamLabel": "My team"
      }
    ]
  }
}
```

Related CLI command: [getEnvironment](udclient_getenvironment.md).

**Parent topic:** [environment resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_environment.md)

