# Get the user or users with a given e-mail address

## Request

```
GET https://{hostname}:{port}
    /cli/user/byEmail?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|email|string|true|E-mail address of the user|
|allUsers|boolean|false|Specify true to retrieve all users with the e-mail address or false to return only the first user that matches the address|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/user/byEmail
  ?email=jsmith@us.ibm.com&allUsers=true" 
  -H "Accept: application/json"

```

## Example response

```
[{"id":"bade154b-c8c9-4aa6-a875-4b56d7132be5","name":"jsmith"},
{"id":"2c1c9012-2111-4d6a-b5f0-b6cabff94713","name":"janesmith"}]
```

Related CLI command: [getUserByEmail](udclient_getuserbyemail.md).

**Parent topic:** [user resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_user.md)

