# getComponentVersions

Get the versions of a component

By default, this command returns only active versions.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentVersions [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|inactive|boolean|false|Specify true to include inactive versions; the default is false|
|numResults|int|false|Specify a number greater than 0 to limit the number of results. If numResults is not specified, or is given to be < 1, no limit is applied.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getComponentVersions
  -component MyComponent
```

## Example response

```
[
  {
    "id": "1a53a4a6-bfcd-4014-a0ab-83f97077a4d4",
    "name": "1",
    "description": "",
    "type": "FULL",
    "created": 1441381421819,
    "active": true,
    "archived": false,
    "sizeOnDisk": 4096
  },
  {
    "id": "ed2361a4-948c-4646-bda4-7465df0e38b5",
    "name": "2",
    "description": "",
    "type": "FULL",
    "created": 1441381420863,
    "active": true,
    "archived": false,
    "sizeOnDisk": 4096
  }
]

```

Related REST command: [Get the versions of a component](rest_cli_component_versions_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

