# login

Log in to the server

This command creates an authentication token on the server. Subsequent udclient commands that you run use this token, so you do not have to specify credentials. The token is recorded locally in the user's home directory in the file .ucd/authToken. The token expires 24 hours after it was created. Use the logout command to delete the token and the authtoken file.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  login
```

## Parameters

None.

## Example

```
udclient -username admin -password admin 
  -weburl https://myserver.example.com:8443
  login
```

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

