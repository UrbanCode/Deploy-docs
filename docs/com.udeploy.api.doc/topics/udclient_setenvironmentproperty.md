# setEnvironmentProperty

Set a property on environment

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setEnvironmentProperty [JSON file]
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
  "environment": "Name or ID of the environment",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setEnvironmentProperty 
  -application JPetStore 
  -environment "Tutorial environment 1" 
  -name Prop1 
  -value value1
```

## Example response

```
{
  "id": "ba3f8bd4-c26e-4529-a2a3-66e283242244",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related REST command: [Set a property on environment](rest_cli_environment_propvalue_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

