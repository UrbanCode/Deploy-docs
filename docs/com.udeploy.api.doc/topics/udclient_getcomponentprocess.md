# getComponentProcess

Get information about a component process

This command returns a JSON representation of a component process.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentProcess [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|componentProcess|string|true|Name or ID of the component process|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentProcess
  -component JPetStore-APP
  -componentProcess "Deploy application component"
```

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

Related REST command: [Get information about a component process](rest_cli_componentprocess_info_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

