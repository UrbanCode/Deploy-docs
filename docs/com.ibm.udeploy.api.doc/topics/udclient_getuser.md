# getUser

List information about a user

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getUser [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getUser 
  -user jsmith
```

## Example response

```
{
  "id": "2507eaaf-c98e-46ee-936d-bc538bee9dc4",
  "name": "jsmith",
  "actualName": "Jane C. Smith",
  "displayName": "Jane C. Smith (jsmith)",
  "email": "jsmith@example.org",
  "deleted": false,
  "deletedDate": 0,
  "authenticationRealm": "20000000000000000000000000000001",
  "isLockedOut": false,
  "isDeletable": true,
  "groups": [
  ]
}
```

Related REST command: [List information about a user](rest_cli_user_info_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

