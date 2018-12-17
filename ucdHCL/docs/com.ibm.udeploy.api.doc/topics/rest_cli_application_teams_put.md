# Add an application to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/application/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Application".|

Related CLI command: [addApplicationToTeam](udclient_addapplicationtoteam.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

