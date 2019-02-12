# setResourceProperty

Set a property on a resource

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setResourceProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application (Required 
  to look up blueprint by name)",
  "blueprint": "Name or ID of the blueprint (optional)",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "resource": "ID of resource or Path to the resource, 
  such as /ResourceGroup/Agents/Agent1",
  "template": "Name or ID of the resource template 
  (optional)",
  "value": "New value for the property (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setResourceProperty
  -resource "/My resource"
  -name property1
  -value value1
```

## Example response

```
{
  "id": "bd20924e-8547-4d41-b9b1-36b41278d224",
  "name": "property1",
  "value": "value1",
  "secure": false
}
```

Related REST command: [Set a property on a resource](rest_cli_resource_setproperty_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

