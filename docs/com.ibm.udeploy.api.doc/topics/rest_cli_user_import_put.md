# Import a user from LDAP

This command adds one or more users from an LDAP realm to the server.

## Request

```
PUT https://{hostname}:{port}
    /cli/user/import?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name or pattern of the users to be imported. Supports wildcard character \*.|
|authenticationRealm|string|true|Authentication realm name or ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

Related CLI command: [importLdapUser](udclient_importldapuser.md).

**Parent topic:** [user resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_user.md)

