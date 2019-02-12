# Add a base resource to an environment

## Request

```
PUT https://{hostname}:{port}
    /cli/environment/addBaseResource?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|
|application|string|false|Name of the application; this value is required if you specify the environment name instead of ID|
|resource|string|true|Path or ID of the resource to add|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/environment/addBaseResource
  ?application=MyApplication&environment=MyEnvironment&resource=/agents/agent1" -X PUT
```

Related CLI command: [addEnvironmentBaseResource](udclient_addenvironmentbaseresource.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

