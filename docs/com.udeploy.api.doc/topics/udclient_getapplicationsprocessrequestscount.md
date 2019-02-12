# getApplicationsProcessRequestsCount

Count all application process requests

This command returns the total number of application process requests for all applications.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getApplicationsProcessRequestsCount [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|startedAfter|long|false|A timestamp, in milliseconds from the UNIX epoch. If you specify this parameter, the server counts all application process requests that were created after the specified timestamp.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getApplicationsProcessRequestsCount
  -startedAfter 1471603999000
```

## Example response

```
{
  "appProcReqCount": 223
}
```

Related REST command: [Count all application process requests](rest_cli_applicationprocessrequest_count_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

