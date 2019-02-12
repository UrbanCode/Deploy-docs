# getSystemProperties

List system properties

This command returns a JSONArray representation of the system properties, which behave like global variables for the server.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getSystemProperties
```

## Parameters

None.

## Example response

```
[
  {
    "id": "af25c8b2-a69a-4d1b-a0ed-ddb226dfac18",
    "name": "System property 1",
    "value": "value001",
    "description": "This is a system property",
    "secure": false
  }
]
```

Related REST command: [List system properties](rest_cli_systemconfiguration_getproperties_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

