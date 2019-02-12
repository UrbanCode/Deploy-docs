# getAllUsersWithEmail

Get all users with a given e-mail address

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getAllUsersWithEmail [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|email|string|true|E-mail address of the user|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  allUsersWithEmail
  -email jsmith@us.ibm.com
  
```

## Example response

```
[{"id":"bade154b-c8c9-4aa6-a875-4b56d7132be5","name":"jsmith"},
{"id":"2c1c9012-2111-4d6a-b5f0-b6cabff94713","name":"janesmith"}]
```

Related REST command: [Get all users with a given e-mail address](rest_cli_user_alluserswithemail_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

