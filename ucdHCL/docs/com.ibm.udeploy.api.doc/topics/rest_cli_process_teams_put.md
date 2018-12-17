# Add a process to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/process/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|process|string|true|Name or ID of the process|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Process".|

Related CLI command: [addProcessToTeam](udclient_addprocesstoteam.md).

**Parent topic:** [process resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_process.md)

