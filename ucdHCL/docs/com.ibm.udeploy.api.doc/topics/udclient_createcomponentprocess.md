# createComponentProcess

Create a new component process

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createComponentProcess [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "active": "true",
  "component": "Component ID",
  "configActionType": "ADD",
  "defaultWorkingDir": "${p:resource/work.dir}/${p:
  component.name}",
  "description": "Description. This template includes 
  three steps: Download Artifacts, Run Groovy, and Run 
  Shell.",
  "inventoryActionType": "ADD",
  "name": "Name of the component process",
  "propDefs": [],
  "rootActivity": {
    "children": [
      {
        "allowFailure": false,
        "children": [],
        "commandName": "Download Artifacts",
        "impersonationUseSudo": false,
        "name": "First step",
        "pluginName": "Urbancode Versioned File Storage",
        "pluginVersion": 16,
        "properties": {
          "artifactSetBaseDir": "",
          "compId": "${p:component.id}",
          "directoryOffset": ".",
          "fileExcludePatterns": "",
          "fileIncludePatterns": "**/*",
          "fullVerification": true,
          "label": "${p:version.name",
          "repositoryId": "${p:
  component/code_station/repository}",
          "repositoryUrl": "${p:server.url}/vfs",
          "resId": "${p:resource.id}",
          "serverUrl": "${p:server.url}",
          "setFileExecuteBits": false,
          "syncMode": true,
          "verifyFileIntegrity": false
        },
        "showHIdden": false,
        "type": "plugin",
        "useImpersonation": false
      },
      {
        "allowFailure": false,
        "children": [],
        "commandName": "Shell",
        "impersonationUseSudo": false,
        "name": "Second step",
        "pluginName": "Shell",
        "pluginVersion": 3,
        "properties": {
          "directoryOffset": ".",
          "outputFile": "",
          "runAsDaemon": false,
          "scriptBody": "echo \"Hello World\"",
          "shellInterpreter": ""
        },
        "showHIdden": false,
        "type": "plugin",
        "useImpersonation": false
      },
      {
        "children": [],
        "name": "FINISH",
        "type": "finish"
      }
    ],
    "edges": [
      {
        "to": "First step",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "from": "First step",
        "to": "Second step",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "from": "Second step",
        "to": "FINISH",
        "type": "ALWAYS",
        "value": ""
      }
    ],
    "name": "GRAPH",
    "offsets": [
      {
        "name": "First step",
        "x": "-65",
        "y": "90"
      },
      {
        "name": "Second step",
        "x": "-70",
        "y": "210"
      },
      {
        "name": "FINISH",
        "x": "-60",
        "y": "450"
      }
    ],
    "type": "graph"
  },
  "status": "Active",
  "takesVersion": "Specify true for a deployment or 
  rollback process; specficy false for an operational (no 
  version needed) process"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createComponentProcess newComponentProcess.json

```

## Example JSON request

```
{
  "name": "My new component process",
  "component": "e84c7947-fad1-4399-8eb8-0d0d354b9e2b"
  "description": "New component process for command example",
  "defaultWorkingDir": "${p:resource\/work.dir}\/${p:component.name}",
  "takesVersion": "false",
  "inventoryActionType": "ADD",
  "status": "Active",
  "configActionType": "ADD",
  "active": "true",
  "propDefs": [
  ],
  "rootActivity": {
    "type": "graph",
    "name": "GRAPH",
    "edges": [
      {
        "to": "First Step",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "to": "Second Step",
        "from": "First Step",
        "type": "ALWAYS",
        "value": ""
      },
      {
        "to": "FINISH",
        "from": "Second Step",
        "type": "ALWAYS",
        "value": ""
      }
    ],
    "offsets": [
      {
        "name": "First Step",
        "x": "-65",
        "y": "90"
      },
      {
        "name": "Second Step",
        "x": "-70",
        "y": "210"
      },
      {
        "name": "FINISH",
        "x": "-60",
        "y": "450"
      }
    ],
    "children": [
      {
        "allowFailure": false,
        "useImpersonation": false,
        "showHIdden": false,
        "impersonationUseSudo": false,
        "commandName": "Download Artifacts",
        "pluginName": "IBM UrbanCode Deploy Versioned File Storage",
        "pluginVersion": 18,
        "type": "plugin",
        "name": "First Step",
        "children": [
        ],
        "properties": {
          "directoryOffset": ".",
          "artifactSetBaseDir": "",
          "fileIncludePatterns": "**\/*",
          "fileExcludePatterns": "",
          "syncMode": true,
          "fullVerification": true,
          "setFileExecuteBits": false,
          "verifyFileIntegrity": false,
          "repositoryUrl": "${p:server.url}\/vfs",
          "repositoryId": "${p:component\/code_station\/repository}",
          "label": "${p:version.name",
          "serverUrl": "${p:server.url}",
          "compId": "${p:component.id}",
          "resId": "${p:resource.id}"
        }
      },
      {
        "allowFailure": false,
        "useImpersonation": false,
        "showHIdden": false,
        "impersonationUseSudo": false,
        "commandName": "Shell",
        "pluginName": "Shell",
        "pluginVersion": 3,
        "type": "plugin",
        "name": "Second Step",
        "children": [
        ],
        "properties": {
          "directoryOffset": ".",
          "shellInterpreter": "",
          "scriptBody": "echo \"Hello World\"",
          "runAsDaemon": false,
          "outputFile": ""
        }
      },
      {
        "type": "finish",
        "name": "FINISH",
        "children": [
        ]
      }
    ]
  }
}
```

## Example response

```
{
  "id": "76f0d90a-b9c5-42d2-a561-6ab1b22a1acb",
  "name": "My new component process",
  "description": "New component process for command example",
  "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
  "takesVersion": false,
  "inventoryActionType": "ADD",
  "status": "Active",
  "active": true,
  "versionCount": 1,
  "version": 1,
  "commit": 0,
  "path": "components/bd486abe-e6e1-43e5-9e0f-f7ad20929bad/processes/76f0d90a-b9c5-42d2-a561-6ab1b22a1acb"
}
```

Related REST command: [Create a new component process](rest_cli_componentprocess_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

