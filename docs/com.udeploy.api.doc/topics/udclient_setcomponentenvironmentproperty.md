# setComponentEnvironmentProperty

Set a component environment property value

This command will set a component property value specifically for this environment.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setComponentEnvironmentProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application; this 
  value is required if you specify the environment name 
  instead of ID",
  "component": "Name or ID of the component",
  "environment": "Name or ID of the environment",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setComponentEnvironmentProperty
  -name Prop1
  -value value1
  -component JPetStore-APP
  -environment Environment1
  -application JPetStore
```

Related REST command: [Set a component environment property value](rest_cli_environment_componentproperties_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

