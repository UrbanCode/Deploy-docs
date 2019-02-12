# Get all users with a given e-mail address

## Request

```
GET https://{hostname}:{port}
    /cli/user/allUsersWithEmail?{parameters}
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
   
  "https://myserver.example.com:8443/cli/user/allUsersWithEmail?email=jsmith@us.ibm.com" 
  -H "Accept: application/json"

```

## Example response

```
[{"id":"bade154b-c8c9-4aa6-a875-4b56d7132be5","name":"jsmith"},
{"id":"2c1c9012-2111-4d6a-b5f0-b6cabff94713","name":"janesmith"}]
```

Related CLI command: [getAllUsersWithEmail](udclient_getalluserswithemail.md).

**Parent topic:** [user resource](../../com.udeploy.api.doc/topics/rest_cli_user.md)

