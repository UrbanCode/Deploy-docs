# getApplicationProcess

Get information about an application process

Returns a JSON representation of an application process.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplicationProcess [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|applicationProcess|string|true|Name of the process|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplicationProcess
  -application JPetStore
  -applicationProcess "Deploy JPetStore"
```

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

Related REST command: [Get information about an application process](rest_cli_applicationprocess_info_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

