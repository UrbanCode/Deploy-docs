# getBlueprintsInApplication

Get all blueprints in an application

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getBlueprintsInApplication [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getBlueprintsInApplication
  -application JPetStore
```

## Example response

```
[
  {
    "id": "7e0a196f-41ca-40e8-aed8-4f47cafcedc9",
    "name": "My blueprint",
    "description": ""
  },
  {
    "id": "362cfc88-e5f7-4d98-aaee-a53edec5c8d2",
    "name": "Other blueprint",
    "description": ""
  }
]
```

Related REST command: [Get all blueprints in an application](rest_cli_application_blueprintsinapplication_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

