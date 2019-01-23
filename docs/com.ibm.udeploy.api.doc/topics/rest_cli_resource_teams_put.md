# Add a resource to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/resource/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Resource".|

Related CLI command: [addResourceToTeam](udclient_addresourcetoteam.md).

**Parent topic:** [resource resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_resource.md)

