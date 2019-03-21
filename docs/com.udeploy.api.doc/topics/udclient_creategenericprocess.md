# createGenericProcess

Create a generic process

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createGenericProcess [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "defaultResourceId": "Default resource ID",
  "description": "Description. This template includes 
  three steps: Download Artifacts, Run Groovy, and Run 
  Shell.",
  "name": "Process name or ID",
  "notificationScheme": "Name of notification scheme",
  "propDefs": [{
    "allowedValues": [{"label": "value"}],
    "defaultLabel": "defaultLabel",
    "description": "description",
    "httpBasePath": "httpBasePath",
    "httpFormat": "httpFormat",
    "httpLabelPath": "httpLabelPath",
    "httpPassword": "httpPassword",
    "httpUrl": "httpurl",
    "httpUsername": "httpUsername",
    "httpValuePath": "httpValuePath",
    "label": "label",
    "name": "name",
    "pattern": "Pattern",
    "required": "required",
    "resolveHttpValuesUrl": "resolveHttpValuesUrl",
    "type": "type",
    "value": "value"
  }],
  "properties": {"Property name": "Property value 
  (Optional)"},
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
  "workingDir": "${p:resource/work.dir}/${p:process.name}"
}

```

Related REST command: [Create a generic process](rest_cli_process_create_put.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

