# Remove an application from a team

## Request

```
DELETE https://{hostname}:{port}
    /cli/application/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application.|
|team|string|true|Name or ID of the team.|
|type|string|false|Name of the security type to use; the default is Standard Application.|

Related CLI command: [removeApplicationFromTeam](udclient_removeapplicationfromteam.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

