# createUser

Create a user

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createUser [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "authenticationRealm": "Authentication realm ID",
  "email": "Email address",
  "name": "User name",
  "password": "Password"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createUser 
  newUser.json
```

## Example JSON request

```
{
  "name": "jsmith",
  "password": "password",
  "actualName": "Jane Smith",
  "email": "jsmith@example.org",
  "authenticationRealm": "Internal Security"
}
```

## Example response

```
{
  "id": "2507eaaf-c98e-46ee-936d-bc538bee9dc4",
  "name": "jsmith",
  "actualName": "Jane Smith",
  "displayName": "Jane Smith (jsmith)",
  "email": "jsmith@example.org",
  "deleted": false,
  "deletedDate": 0,
  "authenticationRealm": "20000000000000000000000000000001",
  "isLockedOut": false,
  "isDeletable": true
}
```

Related REST command: [Create a user](rest_cli_user_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

