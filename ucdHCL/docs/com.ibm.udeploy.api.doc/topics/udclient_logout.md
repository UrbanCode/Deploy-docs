# logout

Log out of the server

This command deletes the authentication token that is currently in use, and deletes the local file that contains information about this token.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  logout
```

## Parameters

None.

## Example

```
udclient 
  -weburl https://myserver.example.com:8443
  logout
```

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

