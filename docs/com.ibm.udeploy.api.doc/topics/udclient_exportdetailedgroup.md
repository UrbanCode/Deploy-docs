# exportDetailedGroup

List the members of a group \(detailed\)

This command lists the members of a group, including IDs and e-mail addresses.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  exportDetailedGroup [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  exportDetailedGroup 
  -group teamA
```

## Example response

```
[
  {
    "userName": "jdoe",
    "userId": "a459dffd-e057-494d-b119-16e85d7cd911",
    "userEmail": "jdoe@example.org"
  },
  {
    "userName": "jsmith",
    "userId": "7794dee7-d4c6-4f6f-b1ce-56c5d3cbfdda",
    "userEmail": "jsmith@example.org"
  }
]

```

Related REST command: [List the members of a group \(detailed\)](rest_cli_group_exportdetailed_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

