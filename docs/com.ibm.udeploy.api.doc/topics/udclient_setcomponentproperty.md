# setComponentProperty

Set a property on a component

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  setComponentProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Name or ID of the component",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property",
  "value": "Value of the property (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setComponentProperty
  -component JPetStore-APP
  -name Prop1
  -value value1
```

## Example response

```
{
  "id": "3702f391-09e1-4550-903a-d5ae286c94aa",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related REST command: [Set a property on a component](rest_cli_component_propvalue_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

