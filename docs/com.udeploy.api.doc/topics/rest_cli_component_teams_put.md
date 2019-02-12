# Add a component to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/component/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Component".|

Related CLI command: [addComponentToTeam](udclient_addcomponenttoteam.md).

**Parent topic:** [component resource](../../com.udeploy.api.doc/topics/rest_cli_component.md)

