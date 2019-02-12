# getEnvironmentsInApplication

Get information about all environments in an application

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getEnvironmentsInApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getEnvironmentsInApplication
  -application JPetStore
```

## Example response

```
[
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
    ]
  }
]
```

Related REST command: [Get information about all environments in an application](rest_cli_application_environmentsinapplication_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

