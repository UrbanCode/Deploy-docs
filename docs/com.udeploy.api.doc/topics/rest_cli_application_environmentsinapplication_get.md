# Get information about all environments in an application

## Request

```
GET https://{hostname}:{port}
    /cli/application/environmentsInApplication?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/application/environmentsInApplication
  ?application=JPetStore"
```

## Example response

```
[
  {
    "id": "1f97af86-cde3-4ba2-803b-0e4580dcc05b",
    "name": "Tutorial environment 1",
    "description": "",
    "color": "#ffffff",
    "requireApprovals": false,
    "lockSnapshots": false,
    "calendarId": "e237199e-8bbc-497e-97eb-ca2568dff91c",
    "active": true,
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "conditions": [
    ]
  }
]
```

Related CLI command: [getEnvironmentsInApplication](udclient_getenvironmentsinapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

