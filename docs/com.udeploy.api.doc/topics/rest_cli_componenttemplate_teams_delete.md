# Remove a component template from a team

## Request

```
DELETE https://{hostname}:{port}
    /cli/componentTemplate/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|componentTemplate|string|true|Name or ID of the component template|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Component Template".|

Related CLI command: [removeComponentTemplateFromTeam](udclient_removecomponenttemplatefromteam.md).

**Parent topic:** [componentTemplate resource](../../com.udeploy.api.doc/topics/rest_cli_componenttemplate.md)

