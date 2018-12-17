# List information about a user

## Request

```
GET https://{hostname}:{port}
    /cli/user/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

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

Related CLI command: [getUser](udclient_getuser.md).

**Parent topic:** [user resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_user.md)

