# getComponentProcessRequestCount

Get the number of component process requests submitted after a certain time

This command returns a count of all the component process requests submitted after a certain time.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentProcessRequestCount [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|submittedAfter|long|false|A timestamp, in milliseconds from the UNIX epoch. If you specify this parameter, the server counts all CPRs that were created after the specified timestamp.|

Related REST command: [Get the number of component process requests submitted after a certain time](rest_cli_componentprocessrequest_count_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

