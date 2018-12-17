# importVersions

Import new component versions

This command polls the source configuration for new component versions. Add property name/value pairs as necessary - this can be used to add specific versions.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  importVersions [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "component": "Component name or ID",
  "properties": {"Source configuration plugin property 
  name": "Property value"}
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  importVersions newVersions.json
```

## Example JSON request

```
{
  "component": "JPetStore-WEB",
  "properties": {
    "Prop1": "value1"
  }
}
```

Related REST command: [Import new component versions](rest_cli_component_integrate_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

