# Create a user

## Request

```
PUT https://{hostname}:{port}
    /cli/user/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "authenticationRealm": "Authentication realm ID",
  "email": "Email address",
  "name": "User name",
  "password": "Password"
}

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

Related CLI command: [createUser](udclient_createuser.md).

**Parent topic:** [user resource](../../com.udeploy.api.doc/topics/rest_cli_user.md)

