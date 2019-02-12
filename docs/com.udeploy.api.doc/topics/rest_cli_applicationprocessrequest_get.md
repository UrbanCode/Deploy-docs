# Get information about all application process requests on the server

This command returns a JSON representation of all application process requests, up to a maximum of 100.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcessRequest?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|startedAfter|long|false|A timestamp, in milliseconds from the UNIX epoch. If you specify this parameter, the server includes the application process requests that were created after the specified timestamp.|
|startIndex|int|false|An index number that specifies the application process request to start with. You can use this index number to page through results.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/applicationProcessRequest
  ?startedAfter=1471603999000&startIndex=200" 

```

## Example response

```
[
  {
    "application": {
      "id": "962d3544-c028-4d44-8d0d-52311043e83d",
      "securityResourceId": "9543d94f-d9b9-4a34-a43a-f4d7d69b9987",
      "name": "MyApplication",
      "description": "",
      "created": 1471534973567,
      "enforceCompleteSnapshots": false,
      "active": true,
      "tags": [],
      "deleted": false,
      "user": "admin"
    },
    "applicationProcess": {
      "id": "4a38f91e-41bb-49c0-8010-d406d65fa7ba",
      "name": "deploy",
      "description": "",
      "active": true,
      "inventoryManagementType": "AUTOMATIC",
      "offlineAgentHandling": "PRE_EXECUTION_CHECK",
      "versionCount": 2,
      "version": 2,
      "commit": 17,
      "path": "applications/962d3544-c028-4d44-8d0d-52311043e83d/processes/4a38f91e-41bb-49c0-8010-d406d65fa7ba",
      "deleted": false,
      "metadataType": "applicationProcess"
    },
    "environment": {
      "id": "8ecf9ba2-4f7a-4326-a4bd-309a0366b2a2",
      "securityResourceId": "fdab7788-519a-4118-87a7-d1e4f0f391c9",
      "name": "local",
      "description": "",
      "color": "#00B2EF",
      "requireApprovals": false,
      "noSelfApprovals": false,
      "lockSnapshots": false,
      "calendarId": "27c132c9-b805-4ece-b6f9-265a1b355c21",
      "active": true,
      "deleted": false,
      "cleanupDaysToKeep": 0,
      "cleanupCountToKeep": 0,
      "enableProcessHistoryCleanup": false,
      "useSystemDefaultDays": true,
      "historyCleanupDaysToKeep": 365,
      "conditions": []
    },
    "id": "3bc33fb8-98a6-4a24-a97b-d6e4b4b541a3",
    "submittedTime": 1471535097984,
    "traceId": "46749e41-d571-4b3c-a3b2-6fd0b6f23858",
    "userName": "admin",
    "onlyChanged": true,
    "description": "",
    "startTime": 1471535098738,
    "result": "SUCCEEDED",
    "state": "CLOSED",
    "paused": false,
    "endTime": 1471535099134,
    "duration": 396
  },
  {
    "application": {
      "id": "8ba25265-f313-4246-aa8a-4f8a9617ed2b",
      "securityResourceId": "10935be7-678d-4dc6-bbd1-57644d619041",
      "name": "MyApplication2",
      "description": "",
      "created": 1471535176734,
      "enforceCompleteSnapshots": false,
      "active": true,
      "tags": [],
      "deleted": false,
      "user": "admin"
    },
    "applicationProcess": {
      "id": "4d4d727c-a92e-45f0-8901-1277e92c09f4",
      "name": "deploy",
      "description": "",
      "active": true,
      "inventoryManagementType": "AUTOMATIC",
      "offlineAgentHandling": "PRE_EXECUTION_CHECK",
      "versionCount": 2,
      "version": 2,
      "commit": 20,
      "path": "applications/8ba25265-f313-4246-aa8a-4f8a9617ed2b/processes/4d4d727c-a92e-45f0-8901-1277e92c09f4",
      "deleted": false,
      "metadataType": "applicationProcess"
    },
    "environment": {
      "id": "03eae7bf-f97f-4e2d-81b5-8780ee1d5277",
      "securityResourceId": "43fa87b2-1751-44d8-9abe-e788d7990608",
      "name": "local",
      "description": "",
      "color": "#00B2EF",
      "requireApprovals": false,
      "noSelfApprovals": false,
      "lockSnapshots": false,
      "calendarId": "79fc6057-f0a6-42a1-be0f-939ac76dbd50",
      "active": true,
      "deleted": false,
      "cleanupDaysToKeep": 0,
      "cleanupCountToKeep": 0,
      "enableProcessHistoryCleanup": false,
      "useSystemDefaultDays": true,
      "historyCleanupDaysToKeep": 365,
      "conditions": []
    },
    "id": "0596ac0b-36c0-449a-a11b-a5aa0cccb98b",
    "submittedTime": 1471535228001,
    "traceId": "e10524ee-e43c-44ea-9a5b-610d6dcbf2e8",
    "userName": "admin",
    "onlyChanged": true,
    "description": "",
    "startTime": 1471535228400,
    "result": "SUCCEEDED",
    "state": "CLOSED",
    "paused": false,
    "endTime": 1471535228502,
    "duration": 102
  }
]
```

Related CLI command: [getApplicationsProcessRequests](udclient_getapplicationsprocessrequests.md).

**Parent topic:** [applicationProcessRequest resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

