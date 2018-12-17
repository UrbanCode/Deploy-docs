# createGroup

Create an empty group

Groups can only be created in Internal Storage authorization realms.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createGroup [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|group|string|true|Name of the group|
|authorizationRealm|string|true|Name of the Internal Storage authorization realm|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createGroup 
  -group group1 
  -authorizationRealm "Internal Security"
```

**Note:** Adding groups to LDAP and SSO realms is deprecated.

## Example response

```
{
  "id": "a5be904f-d65a-41ae-9bfd-0a0384c90eeb",
  "name": "group1",
  "enabled": true
}
```

Related REST command: [Create an empty group](rest_cli_group_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

