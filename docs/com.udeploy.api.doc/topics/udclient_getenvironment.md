# getEnvironment

Get information about an environment

This command returns a JSON representation of an environment.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getEnvironment [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getEnvironment 
  -application JPetStore 
  -environment "Tutorial environment 1"
```

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

Related REST command: [Get information about an environment](rest_cli_environment_info_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

