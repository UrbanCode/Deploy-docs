# createAuthToken

Create an authorization token

Tokens provide authorization for agents, users, and external systems or applications.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createAuthToken [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|user|string|true|The user this token is associated with|
|expireDate|string|true|Expiration date and time of the token, in the format MM-DD-YYYY-HH:mm|
|description|string|false|Description of the authorization token|
|allowedIps|string|false|Allowed IP addresses in CIDR notation, such as 192.169.1.0/24|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createAuthToken
  -user admin
  -expireDate 12-31-2020-12:00
```

## Example response

```
{"token":"42ece458-b197-4c2e-92a0-c63e10fd9b4f"}
```

Related REST command: [Create an authorization token](rest_cli_teamsecurity_tokens_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

