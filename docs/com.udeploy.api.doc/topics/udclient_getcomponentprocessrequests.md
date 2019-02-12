# getComponentProcessRequests

Get information about all component process requests

This command returns a JSON representation of a list of up to 100 component process requests at a time.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getComponentProcessRequests [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|submittedAfter|long|false|Time value that marks the oldest CPR we want to retrieve.|

Related REST command: [Get information about all component process requests](rest_cli_componentprocessrequest_info_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

