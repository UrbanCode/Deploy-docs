# Update a user

Specify the user name in the 'user' parameter and use the JSON string to specify new information about the user. This command can update the name and email address of the user, but not the password.

## Request

```
PUT https://{hostname}:{port}
    /cli/user/update?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|Name of the user|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "actualName": "User real name (optional)",
  "email": "Email address (optional)"
}

```

## Example JSON request

```
{
  "password": "password",
  "actualName": "Jane Smith",
  "email": "jsmith@example.org"
}
```

Related CLI command: [updateUser](udclient_updateuser.md).

**Parent topic:** [user resource](../../com.udeploy.api.doc/topics/rest_cli_user.md)

