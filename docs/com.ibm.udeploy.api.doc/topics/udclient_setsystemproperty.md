# setSystemProperty

Set a system property

System properties behave like global variables for the server.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  setSystemProperty [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
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
  setSystemProperty
  -name "System property 1"
  -value value001
```

## Example response

```
{
  "id": "f3bec2ee-3f3e-461f-b5b0-e844efafbdbe",
  "name": "System property 1",
  "value": "value001",
  "secure": false
}
```

Related REST command: [Set a system property](rest_cli_systemconfiguration_propvalue_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

