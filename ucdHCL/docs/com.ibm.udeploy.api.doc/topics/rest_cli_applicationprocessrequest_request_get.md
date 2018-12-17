# Get an application process request's activity trace.

## Request

```
GET https://{hostname}:{port}
    /cli/applicationProcessRequest/{request}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|request|string|true|The ID of the application process request.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -k -u jsmith:passwd 
   
  "https://myserver.example.com:8443/cli/
  applicationProcessRequest/151cd268-ef32-4e55-903b-86ee66314e1e"
```

## Example response

```
{
  "id": "8cbccccf-581e-4500-af41-1d0429ef2dae",
  "type": "graph",
  "name": "2da0c9e5-0045-45b3-a49e-6f130afa0305",
  "state": "EXECUTING",
  "result": "NONE",
  "startDate": 1441394363997,
  "duration": 9052,
  "paused": false,
  "workflowTraceId": "193e892f-677d-4534-9763-ff8d005a5829",
  "children": [
    {
      "id": "bcbc874b-bbd9-4c6c-8890-3575373bc07f",
      "type": "runProcess",
      "displayName": "Run generic process",
      "name": "MyGenericProcess",
      "state": "EXECUTING",
      "result": "NONE",
      "startDate": 1441394363997,
      "duration": 9052,
      "workflowTraceId": "193e892f-677d-4534-9763-ff8d005a5829",
      "childRequestId": "94c77d8d-e6d2-41fd-aa8d-61f606c438e5",
      "graphPosition": 1
    },
    {
      "id": "a9ef585b-ff08-4b25-bd4d-fe7295a8882e",
      "type": "componentEnvironmentIterator",
      "displayName": "Install Component 2",
      "name": "3f13d0d7d892af1b135251d94583a9",
      "state": "INITIALIZED",
      "result": "NONE",
      "duration": 1441394373049,
      "workflowTraceId": "193e892f-677d-4534-9763-ff8d005a5829",
      "component": {
        "id": "92c2b418-b3f1-4a5b-bfb7-a88ff5d6c268",
        "securityResourceId": "63a4fe6e-1a8a-4d1e-8122-4f0abca2faa4",
        "name": "Component 2",
        "description": "",
        "created": 1441381387613,
        "componentType": "STANDARD",
        "ignoreQualifiers": 0,
        "importAutomatically": false,
        "useVfs": true,
        "active": true,
        "integrationFailed": false,
        "deleted": false,
        "defaultVersionType": "FULL",
        "cleanupDaysToKeep": 0,
        "cleanupCountToKeep": 0,
        "tags": [],
        "user": "admin"
      },
      "graphPosition": 2
    },
    {
      "id": "326a0b17-360a-43cf-9645-7f58264db996",
      "type": "componentEnvironmentIterator",
      "displayName": "Install Component 1",
      "name": "8eb1ec1009597252ce10c89e2b948b",
      "state": "INITIALIZED",
      "result": "NONE",
      "duration": 1441394373137,
      "workflowTraceId": "193e892f-677d-4534-9763-ff8d005a5829",
      "component": {
        "id": "23742526-8105-4146-bcf1-e4fce1734805",
        "securityResourceId": "9e4cca84-83f2-42ed-b970-3003fef92dd5",
        "name": "Component 1",
        "description": "",
        "created": 1441385679966,
        "componentType": "STANDARD",
        "ignoreQualifiers": 0,
        "importAutomatically": false,
        "useVfs": true,
        "active": true,
        "integrationFailed": false,
        "deleted": false,
        "defaultVersionType": "FULL",
        "cleanupDaysToKeep": 0,
        "cleanupCountToKeep": 0,
        "tags": [],
        "user": "admin"
      },
      "graphPosition": 3
    }
  ]
}

```

Related CLI command: [getApplicationProcessExecution](udclient_getapplicationprocessexecution.md).

**Parent topic:** [applicationProcessRequest resource](../../com.ibm.udeploy.api.doc/topics/rest_cli_applicationprocessrequest.md)

