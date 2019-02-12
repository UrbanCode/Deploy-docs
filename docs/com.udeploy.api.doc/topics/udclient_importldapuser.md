# importLdapUser

Import a user from LDAP

This command adds one or more users from an LDAP realm to the server.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  importLdapUser [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name or pattern of the users to be imported. Supports wildcard character \*.|
|authenticationRealm|string|true|Authentication realm name or ID|

Related REST command: [Import a user from LDAP](rest_cli_user_import_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

