# updateResource

Update a resource

To update a resource with this command, you must specify all of the existing data for the resource.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  updateResource [parameters] [JSON file]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agent": "Name or ID of an agent to use for automation 
  (Optional)",
  "agentPool": "Name or ID of an agent pool to use for 
  automation (Optional)",
  "component": "Name or ID of a component to associate 
  with the resource (Optional)",
  "componentTag": "Name or ID of a component tag to 
  associate with the resource; any components with that tag 
  can be deployed to this resource (Optional)",
  "description": "Description",
  "impersonationForce": "Specify true to prevent children 
  or steps from specifying their own impersonation settings 
  (Optional)",
  "impersonationGroup": "Group for default impersonation 
  (Optional)",
  "impersonationPassword": "Password for default 
  impersonation (Optional)",
  "impersonationUseSudo": "Specify true to use the sudo 
  command for impersonation (Optional)",
  "impersonationUser": "User name for default 
  impersonation (Optional)",
  "name": "Name for the new resource; leave blank to 
  inherit the name from an agent, pool, or role",
  "parent": "ID or path to parent resource; leave blank to 
  create a root resource (Optional)",
  "role": "Name or ID of a resource role to associate with 
  the agent; if this resource is for a component, specify 
  the component name instead (Optional)",
  "roleProperties": {"Property name": "Property value 
  (Optional)"}
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  updateResource 
  -resource "/My resource"
  updateResource.json
```

## Example JSON request

```
{
  "name": "New resource name",
  "description": "An updated resource",
}
```

Related REST command: [Update a resource](rest_cli_resource_update_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

