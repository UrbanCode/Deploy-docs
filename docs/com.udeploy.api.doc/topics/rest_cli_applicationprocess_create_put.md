# Create an application process

## Request

```
PUT https://{hostname}:{port}
    /cli/applicationProcess/create
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "application": "Application ID",
  "description": "Description. This template includes one 
  step, which deploys a component.",
  "inventoryManagementType": "The inventory management for 
  the process request, such as AUTOMATIC",
  "name": "Application process name",
  "offlineAgentHandling": "PRE_EXECUTION_CHECK",
  "propDefs": [{
    "label": "Property label",
    "name": "Property name",
    "type": "TEXT"
  }],
  "properties": [{
    "description": "Description",
    "name": "Property name",
    "secure": true,
    "value": "Property value"
  }],
  "requiredRoleId": "Required Role Name or ID",
  "rootActivity": {
    "children": [
      {
        "children": [{
          "children": [{
            "allowFailure": false,
            "children": [],
            "componentName": "Component name",
            "componentProcessName": "Component process 
  name",
            "name": "First step name",
            "properties": {},
            "type": "componentProcess"
          }],
          "componentName": "Component name",
          "name": "inventoryVersionCheck",
          "status": "Active",
          "type": "inventoryVersionDiff"
        }],
        "componentName": "Component name",
        "failFast": "false",
        "maxIteration": "-1",
        "name": "First step name",
        "runOnlyOnFirst": "false",
        "type": "componentEnvironmentIterator"
      },
      {
        "children": [],
        "name": "FINISH",
        "type": "finish"
      }
    ],
    "edges": [
      {
        "to": "First step name",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "from": "First step name",
        "to": "FINISH",
        "type": "ALWAYS",
        "value": ""
      }
    ],
    "name": "GRAPH",
    "offsets": [
      {
        "name": "First step name",
        "x": "-35",
        "y": "210"
      },
      {
        "name": "FINISH",
        "x": "0",
        "y": "420"
      }
    ],
    "propDefs": [],
    "type": "graph",
    "versionPresets": []
  }
}

```

## Example JSON request

To use an existing application process as a template, follow these steps:

1.  Open the application process in the editor.
2.  In your web browser, open the developer tools or install an extension that shows the network traffic from your browser to the server.
3.  In the process editor, make a change to the application process. This change can be a trivial change, such as moving a step slightly. The process must need to be saved.
4.  Save the application process.
5.  In the web browser developer tools, find the REST PUT call to the endpoint `https://hostName:port/rest/deploy/applicationProcess/applicationProcessID/saveActivities`, where `hostname` and `port` are the host name and port of your server, and `applicationProcessID` is the ID of the application process. This PUT call is the call that sends the new version of the application process to the server.
6.  Find the JSON payload of the REST PUT call. This code describes the steps in the process and the location of the steps on the editor. This payload starts with the code `{"type":"graph","layoutMode":`.
7.  Copy the content of the JSON payload into the rootActivity property of your JSON request.
8.  Update the other properties of the JSON request, such as name and description.

The following example request creates an application process that deploys a component.

```
{
  "name": "My new application process",
  "application": "79f33ffb-9d72-4967-9146-dc252eaea706",
  "description": "New application process for command example",
  "inventoryManagementType": "AUTOMATIC",
  "offlineAgentHandling": "PRE_EXECUTION_CHECK",
  "rootActivity": {
    "type": "graph",
    "name": "GRAPH",
    "edges": [
      {
        "to": "Deploy component",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "to": "FINISH",
        "from": "Deploy component",
        "type": "ALWAYS",
        "value": ""
      }
    ],
    "offsets": [
      {
        "name": "Deploy component",
        "x": "-35",
        "y": "210"
      },
      {
        "name": "FINISH",
        "x": "0",
        "y": "420"
      }
    ],
    "children": [
      {
        "componentName": "Component Y",
        "failFast": "false",
        "runOnlyOnFirst": "false",
        "maxIteration": "-1",
        "type": "componentEnvironmentIterator",
        "name": "Deploy component",
        "children": [
          {
            "componentName": "Component Y",
            "status": "Active",
            "type": "inventoryVersionDiff",
            "name": "inventoryVersionCheck",
            "children": [
              {
                "componentName": "Component Y",
                "componentProcessName": "Deploy Component Y",
                "allowFailure": false,
                "properties": {
                },
                "type": "componentProcess",
                "name": "Deploy component",
                "children": [
                ]
              }
            ]
          }
        ]
      },
      {
        "type": "finish",
        "name": "FINISH",
        "children": [
        ]
      }
    ],
    "propDefs": [
    ]
  }
}
```

## Example response

```
{
  "id": "80d98207-3012-4d9f-858e-0b3aea2ce489",
  "name": "My new application process",
  "description": "New application process for command example",
  "active": true,
  "inventoryManagementType": "AUTOMATIC",
  "offlineAgentHandling": "PRE_EXECUTION_CHECK",
  "versionCount": 1,
  "version": 1,
  "commit": 0,
  "path": "applications/79f33ffb-9d72-4967-9146-dc252eaea706/processes/80d98207-3012-4d9f-858e-0b3aea2ce489"
}
```

Related CLI command: [createApplicationProcess](udclient_createapplicationprocess.md).

**Parent topic:** [applicationProcess resource](../../com.udeploy.api.doc/topics/rest_cli_applicationprocess.md)

