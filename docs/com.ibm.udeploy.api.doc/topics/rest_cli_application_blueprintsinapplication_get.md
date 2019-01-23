# Get all blueprints in an application

## Request

```
GET https://{hostname}:{port}
    /cli/application/blueprintsInApplication?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|application|string|true|Name or ID of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "7e0a196f-41ca-40e8-aed8-4f47cafcedc9",
    "name": "My blueprint",
    "description": ""
  },
  {
    "id": "362cfc88-e5f7-4d98-aaee-a53edec5c8d2",
    "name": "Other blueprint",
    "description": ""
  }
]
```

Related CLI command: [getBlueprintsInApplication](udclient_getblueprintsinapplication.md).

**Parent topic:** [application resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_application.md)

