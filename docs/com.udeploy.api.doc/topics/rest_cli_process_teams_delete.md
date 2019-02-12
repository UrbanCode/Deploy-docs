# Remove a process from a team

## Request

```
DELETE https://{hostname}:{port}
    /cli/process/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|process|string|true|Name or ID of the process.|
|team|string|true|Name or ID of the team.|
|type|string|false|Name of the security type to use; the default is Standard Process.|

Related CLI command: [removeProcessFromTeam](udclient_removeprocessfromteam.md).

**Parent topic:** [process resource](../../com.udeploy.api.doc/topics/rest_cli_process.md)

