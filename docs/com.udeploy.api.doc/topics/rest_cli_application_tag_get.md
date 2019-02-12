# List all tags on an application

## Request

```
GET https://{hostname}:{port}
    /cli/application/tag?{parameters}
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
   
  "https://myserver.example.com:8443/cli/application/tag
  ?application=JPetStore"
```

## Example response

```
[
  {
    "id": "f3c52993-ffe4-464a-b34c-0abc1df7f995",
    "name": "Tag1",
    "color": "#dda0dd",
    "description": "",
    "objectType": "Application"
  },
  {
    "id": "ae47b2dc-8153-42c9-8094-207703a439e4",
    "name": "Tag2",
    "color": "#ffff00",
    "description": "",
    "objectType": "Application"
  }
]
```

Related CLI command: [getTagsOnApplication](udclient_gettagsonapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

