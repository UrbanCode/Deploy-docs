# getStatusList

Get a list of statuses on a snapshot

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getStatusList [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|snapshot|string|true|Name or ID of the snapshot.|
|application|string|false|Name or ID of the application; this value is required if you specify the snapshot name instead of ID.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getStatusList
  -application MyApplication
  -snapshot MySnapshot
```

## Example response

```
[
  {
    "id": "5ab6cc4f-393f-4fa2-ac35-d30e282648c4",
    "type": "SNAPSHOT",
    "name": "Good",
    "description": "",
    "deleted": false,
    "color": "#FFCF01",
    "unique": false,
    "created": 1450130997618
  },
  {
    "id": "51259a1f-69bc-4a3a-b1f4-c1d391b7794a",
    "type": "SNAPSHOT",
    "name": "Interesting",
    "description": "",
    "deleted": false,
    "color": "#007670",
    "unique": false,
    "created": 1450131001305
  }
]

```

Related REST command: [Get a list of statuses on a snapshot](rest_cli_snapshot_getstatuslist_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

