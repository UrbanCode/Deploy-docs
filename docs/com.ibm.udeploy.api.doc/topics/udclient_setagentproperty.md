# setAgentProperty

Set a property on a agent

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  setAgentProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "agent": "Name or ID of the agent",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "value": "New value for the property (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setAgentProperty
  -agent Agent1
  -name Prop1
  -value value1
```

## Example response

```
{
  "id":"cdf5e901-f19a-48b8-82fc-c92c256e31df",
  "name":"newProperty",
  "value":"newValue",
  "secure":false
}
```

Related REST command: [Set a property on a agent](rest_cli_agentcli_setproperty_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

