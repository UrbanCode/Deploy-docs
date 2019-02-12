# Get the latest snapshot deployed to an environment

## Request

```
GET https://{hostname}:{port}
    /cli/environment/{environment}/snapshot?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|false|Name or ID of the application; this value is required if you specify the environment name instead of ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environment|string|true|Name or ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  environment/MyEnvironment/snapshot?application=MyApplication"
```

## Example response

```
{
  "id": "2ef3189b-af8f-49f1-8476-a3d4ed440722",
  "name": "Snap5",
  "created": 1441388592826,
  "active": true,
  "versionsLocked": false,
  "configLocked": false,
  "applicationId": "2d741420-fd31-443d-95eb-472d334f8ec9",
  "user": "admin"
}

```

Related CLI command: [getLatestSnapshotForEnvironment](udclient_getlatestsnapshotforenvironment.md).

**Parent topic:** [environment resource](../../com.udeploy.api.doc/topics/rest_cli_environment.md)

