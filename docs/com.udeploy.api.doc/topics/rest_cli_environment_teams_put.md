# Add an environment to a team

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/teams?{parameters}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|
|environment|string|true|Name or ID of the environment|
|team|string|true|Name or ID of the team|
|type|string|false|Name of the type to use. Leave blank if you are using the type "Standard Application".|

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/environment/teams?
  ?application=MyApplication&environment=MyEnvironment&team=MyTeam" -X PUT
```

Related CLI command: [addEnvironmentToTeam](udclient_addenvironmenttoteam.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

