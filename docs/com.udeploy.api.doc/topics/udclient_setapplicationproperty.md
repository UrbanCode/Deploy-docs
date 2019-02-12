# setApplicationProperty

Set a property on an application

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  setApplicationProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Name or ID of the application",
  "isSecure": "Whether the property is secure; the default 
  is the current state of the property, or false if the 
  property is not yet specified (optional)",
  "name": "Property name",
  "value": "Property value (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  setApplicationProperty
  -application JPetStore
  -name Prop4
  -value value4
```

## Example response

```
{
  "id": "7b818dfe-efd9-465a-bee3-775f60dc297d",
  "name": "Prop4",
  "value": "value4",
  "secure": false
}
```

Related REST command: [Set a property on an application](rest_cli_application_propvalue_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

