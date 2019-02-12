# Get the first user with a given e-mail address

## Request

```
GET https://{hostname}:{port}
    /cli/user/firstUserWithEmail?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|email|string|true|E-mail address of the user|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/user/firstUserWithEmail?email=jsmith@us.ibm.com" 
  -H "Accept: application/json"

```

## Example response

```
{"id":"2c1c9012-2111-4d6a-b5f0-b6cabff94713","name":"janesmith"}
```

Related CLI command: [getFirstUserWithEmail](udclient_getfirstuserwithemail.md).

**Parent topic:** [user resource](../../com.udeploy.api.doc/topics/rest_cli_user.md)

