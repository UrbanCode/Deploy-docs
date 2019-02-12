# setVersionProperty

Set a property on a component version

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setVersionProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Name or ID of the component; this value is 
  required if you specify the version name instead of ID",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Name of the property to set",
  "value": "Value of the property to set (optional)",
  "version": "Name or ID of the version"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setVersionProperty
  -component JPetStore-APP
  -version 1.0
  -name Prop1
  -value value1
```

## Example response

```
{
  "id": "33528ab5-a7be-46cb-9f0c-916a42bd2f62",
  "name": "Prop1",
  "value": "value1",
  "secure": false
}
```

Related REST command: [Set a property on a component version](rest_cli_version_versionproperties_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

