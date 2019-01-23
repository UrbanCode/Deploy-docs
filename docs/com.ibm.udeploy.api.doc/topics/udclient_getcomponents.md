# getComponents

Get information about all components on the server

This command returns a JSON representation of all components on the server.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getComponents [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|active|boolean|false|Specify true \(the default\) to include active components|
|inactive|boolean|false|Specify true to include inactive components; the default is false|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponents
```

## Example response

```
[
  {
    "id": "69a6a5bd-583b-4b40-bd47-54b28f5aa1e6",
    "name": "JPetStore-APP",
    "description": "",
    "created": 1387315824908,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
      {
        "id": "d140ae5a-dfb0-477a-910b-762cc0d99cc6",
        "name": "Tag2",
        "color": "#7fff00",
        "description": "",
        "objectType": "Component"
      }
    ],
    "user": "admin"
  },
  {
    "id": "f4a37f52-7d96-4fb5-b43b-57166b177e7c",
    "name": "JPetStore-DB",
    "description": "",
    "created": 1387316389625,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
    ],
    "user": "admin"
  },
  {
    "id": "76299d8e-c328-42f4-99ab-aa7bfee7aa14",
    "name": "JPetStore-WEB",
    "description": "",
    "created": 1387316469977,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
    ],
    "user": "admin"
  }
]
```

Related REST command: [Get information about all components on the server](rest_cli_component_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

