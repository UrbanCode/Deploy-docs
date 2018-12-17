# exportGroup

List the members of a group

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  exportGroup [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  exportGroup 
  -group group1
```

## Example response

```
{
  "name": "group1",
  "users": [
    "jsmith",
    "jdoe"
  ]
}
```

Related REST command: [List the members of a group](rest_cli_group_export_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

