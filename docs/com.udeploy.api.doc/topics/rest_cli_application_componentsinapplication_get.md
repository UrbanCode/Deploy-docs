# Get all components in an application

## Request

```
GET https://{hostname}:{port}
    /cli/application/componentsInApplication?{parameters}
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
   
  "https://myserver.example.com:8443/cli/application/componentsInApplication
  ?application=JPetStore"
```

## Example response

```
[
  {
    "id": "69a6a5bd-583b-4b40-bd47-54b28f5aa1e6",
    "name": "JPetStore-APP",
    "description": "",
    "created": 1387315824908,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
    ],
    "user": "admin"
  },
  {
    "id": "f4a37f52-7d96-4fb5-b43b-57166b177e7c",
    "name": "JPetStore-DB",
    "description": "",
    "created": 1387316389625,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
    ],
    "user": "admin"
  },
  {
    "id": "76299d8e-c328-42f4-99ab-aa7bfee7aa14",
    "name": "JPetStore-WEB",
    "description": "",
    "created": 1387316469977,
    "importAutomatically": false,
    "useVfs": true,
    "active": true,
    "deleted": false,
    "defaultVersionType": "FULL",
    "cleanupDaysToKeep": 0,
    "cleanupCountToKeep": 0,
    "tags": [
    ],
    "user": "admin"
  }
]
```

Related CLI command: [getComponentsInApplication](udclient_getcomponentsinapplication.md).

**Parent topic:** [application resource](../../com.udeploy.api.doc/topics/rest_cli_application.md)

