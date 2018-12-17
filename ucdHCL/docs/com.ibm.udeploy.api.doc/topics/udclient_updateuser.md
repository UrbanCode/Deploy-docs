# updateUser

Update a user

Specify the user name in the 'user' parameter and use the JSON string to specify new information about the user. This command can update the name and email address of the user, but not the password.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  updateUser [parameters] [JSON file]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "actualName": "User real name (optional)",
  "email": "Email address (optional)"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  updateUser 
  -user jsmith
  updateUser.json
```

## Example JSON request

```
{
  "password": "password",
  "actualName": "Jane Smith",
  "email": "jsmith@example.org"
}
```

Related REST command: [Update a user](rest_cli_user_update_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

