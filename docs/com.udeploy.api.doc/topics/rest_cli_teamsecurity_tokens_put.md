# Create an authorization token

Tokens provide authorization for agents, users, and external systems or applications.

## Request

```
PUT https://{hostname}:{port}
    /cli/teamsecurity/tokens?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|The user this token is associated with|
|expireDate|string|true|Expiration date and time of the token, in the format MM-DD-YYYY-HH:mm|
|description|string|false|Description of the authorization token|
|allowedIps|string|false|Allowed IP addresses in CIDR notation, such as 192.169.1.0/24|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/teamsecurity/tokens?
  user=admin&expireDate=12-31-2020-12:00" -X PUT
```

## Example response

```
{"token":"42ece458-b197-4c2e-92a0-c63e10fd9b4f"}
```

Related CLI command: [createAuthToken](udclient_createauthtoken.md).

**Parent topic:** [teamsecurity resource](../../com.udeploy.api.doc/topics/rest_cli_teamsecurity.md)

