# getApplicationProcessUnfilledProperties

List properties that must be specified for a process

If a snapshot name or ID is specified, results include any component process steps which have some properties marked to receive values later for a specific version based on the snapshot.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplicationProcessUnfilledProperties [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|processName|string|true|Name of the application process|
|snapshot|string|false|Name or ID of the snapshot|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplicationProcessUnfilledProperties
  -application MyApplication
  -processName MyProcess
```

## Example response

```
[
  {
    "id": "decc3570-17ae-4b46-b640-6a7180edafa9",
    "name": "MyProperty",
    "label": "MyProperty",
    "pattern": "",
    "type": "TEXT",
    "value": "",
    "required": false,
    "description": "",
    "placeholder": ""
  }
]
```

Related REST command: [List properties that must be specified for a process](rest_cli_applicationprocess_unfilledproperties_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

