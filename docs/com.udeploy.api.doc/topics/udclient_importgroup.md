# importGroup

Import a group

Specify the details about the group in the JSON file. You can list one or more members of the new group in the 'users' array, or you can leave the array blank to create an empty group. Groups can be created only in Internal Storage authorization realms.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  importGroup [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "authorizationRealm": "Authorization realm name",
  "name": "Group name",
  "users": ["User names"]
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  importGroup newGroup.json
```

## Example JSON request

```
{
  "name": "group1",
  "authorizationRealm": "Internal Security",
  "users": [
    "jdoe",
    "jsmith"
  ]
}
```

## Example response

```
{
  "id": "9dc44e77-e241-480e-8fbb-50f84b64b24b",
  "name": "group1",
  "enabled": true
}
```

Related REST command: [Import a group](rest_cli_group_import_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

