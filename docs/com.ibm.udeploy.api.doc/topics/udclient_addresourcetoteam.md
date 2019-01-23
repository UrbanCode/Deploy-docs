# addResourceToTeam

Add a resource to a team

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  addResourceToTeam [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Resource".|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addResourceToTeam
  -resource /Resource1/Subresource1
  -team MyTeam
```

Related REST command: [Add a resource to a team](rest_cli_resource_teams_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

