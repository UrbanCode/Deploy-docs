# Deploying applications by using REST commands: An example

The following example describes how to use the REST commands to deploy an application.

This example shows the use of the Linux™ curl program to run REST commands. You can use many different programs or programming languages to run REST commands. The code authenticates with the server by specifying the user name and password on the command line. To learn more about running REST commands and authentication, see [Running REST commands](rest_api_ref_using.md) and [Authenticating for REST commands](rest_api_ref_authenticating.md).

The server that is used in this example is server.example.com. The user is nsmith and the password is passwd.

1.  Create and import a component. 
    1.  Use the createComponent PUT command to create the component.

        ```
        curl -k -u nsmith:passwd
          https://server.example.com:8443/cli/component/create
          -X PUT -d @newComponent.json
        ```

        **Note:** You must enter commands on a single line. Commands are split onto different lines here for clarity.

        The following JSON file represents the component:

        ```
        {
          "name": "helloWorld",
          "description": "",
          "importAutomatically": false,
          "useVfs": true,
          "sourceConfigPlugin": "File System (Versioned)",
          "defaultVersionType": "FULL",
          "properties": {
            "FileSystemVersionedComponentProperties/basePath": "/home/user1/artifacts/shared/helloWorld"
          }
        }
        ```

        The command returns a result that is similar to the following JSON information:

        ```
        {
          "id":"cf355787-a772-4533-be45-3e169e9da6eb",
          "securityResourceId":"23504603-ab8c-4740-bc2d-d18c08f790e9",
          "name":"helloWorld",
          "description":"",
          "created":1396878409753,
          "importAutomatically":false,
          "useVfs":true,
          "active":true,
          "integrationFailed":false,
          "deleted":false,
          "defaultVersionType":"FULL",
          "cleanupDaysToKeep":0,
          "cleanupCountToKeep":0,
          "tags":[],
          "user":"nsmith"
        }
        ```

    2.  Use the setComponentProperty PUT command to set a component property.

        ```
        curl -k -u nsmith:passwd 
          "https://server.example.com:8443/cli/
          component/propValue?component=helloWorld&name=helloHome&value=c%3A%5ChelloWorld" -X PUT
        ```

        The command returns a result similar to the following JSON information:

        ```
        {
          "id":"194b6e0c-3f30-4d9a-b3cf-dd61dd1a7328",
          "name":"helloHome",
          "value":"c:\\helloWorld",
          "secure":false
        }
        ```

    3.  Use the importVersions PUT command to import the component version.

        ```
        curl -k -u nsmith:passwd 
          https://server.example.com:8443/cli/component/integrate
          -X PUT -d {"component":"helloWorld"}
        ```

        The command returns the following result:

        ```
        {}
        ```

2.  Use the createComponentProcess PUT command to create a component process.

    ```
    curl -k -u nsmith:passwd
      https://server.example.com:8443/cli/componentProcess/create
      -X PUT -d @componentProcess.json
    
    ```

    The following JSON file represents this component process:

    ```
    {
      "active": "true",
      "component": "helloWorld",
      "configActionType": "ADD",
      "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
      "description": "",
      "inventoryActionType": "ADD",
      "name": "helloProcess",
      "propDefs": [],
      "rootActivity": {
        "children": [
          {
            "allowFailure": false,
            "children": [],
            "commandName": "Delete Files and Directories",
            "impersonationUseSudo": false,
            "name": "Clean work space",
            "pluginName": "File Utils",
            "pluginVersion": 31,
            "properties":{
                "baseDir":".",
                "includes":"*",
                "excludes":"",
                "followSymlinks":"false",
                "caseSensitive":"true"
             },
            "showHidden": false,
            "type": "plugin",
            "useImpersonation": false
          },
          {
            "allowFailure": false,
            "children": [],
            "commandName": "Download Artifacts",
            "impersonationUseSudo": false,
            "name": "Download Artifacts",
            "pluginName": "IBM UrbanCode Deploy Versioned File Storage",
            "pluginVersion": 18,
            "properties":{
               "directoryOffset":".",
               "artifactSetBaseDir":"",
               "fileIncludePatterns":"**/*",
               "fileExcludePatterns":"",
               "syncMode":"true",
               "fullVerification":"true",
               "setFileExecuteBits":"false",
               "verifyFileIntegrity":"false",
               "repositoryUrl":"${p:server.url}/vfs",
               "repositoryId":"${p:component/code_station/repository}",
               "label":"${p:version.name}",
               "serverUrl":"${p:server.url}",
               "compId":"${p:component.id}",
               "resId":"${p:resource.id}",
               "charset":""
            },
            "showHidden": false,
            "type": "plugin",
            "useImpersonation": false
          },
          {
             "allowFailure":false,
             "children": [],
             "commandName":"Create .zip File",
             "impersonationUseSudo":false,
             "name":"Compress artifacts",
             "pluginName":"File Utils",
             "pluginVersion":31,
             "properties":{
                "zipName":"helloWorld.zip",
                "baseDir":".",
                "includes":"*",
                "excludes":"",
                "update":"false",
                "followSymlinks":"false",
                "caseSensitive":"true"
             },
            "showHidden": false,
            "type": "plugin",
            "useImpersonation": false
          },
          {
             "allowFailure":false,
             "children": [],
             "commandName":"Move Directory",
             "impersonationUseSudo":false,
             "name":"Deploy artifacts",
             "pluginName":"File Utils",
             "pluginVersion":31,
             "properties":{
                "sourceDir":".",
                "destDir":"${p:helloHome}/target",
                "includes":"*.zip",
                "excludes":"",
                "mapperRules":""
             },
            "showHidden": false,
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
            "to": "Clean work space",
            "type": "ALWAYS",
            "value": ""
          },
          {
            "from": "Clean work space",
            "to": "Download Artifacts",
            "type": "ALWAYS",
            "value": ""
          },
          {
            "from": "Download Artifacts",
            "to": "Compress artifacts",
            "type": "ALWAYS",
            "value": ""
          },
          {
            "from": "Compress artifacts",
            "to": "Deploy artifacts",
            "type": "ALWAYS",
            "value": ""
          },
          {
            "from": "Deploy artifacts",
            "to": "FINISH",
            "type": "ALWAYS",
            "value": ""
          }
        ],
        "name": "GRAPH",
        "offsets": [
          {
            "name": "Clean work space",
            "x": "-65",
            "y": "90"
          },
          {
            "name": "Download Artifacts",
            "x": "-70",
            "y": "210"
          },
          {
            "name": "Compress artifacts",
            "x": "-70",
            "y": "290"
          },
          {
            "name": "Deploy artifacts",
            "x": "-65",
            "y": "370"
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
      "takesVersion": "true"
    }
    ```

    The command returns a result that is similar to the following JSON information:

    ```
    {
      "id":"12f65517-5fc1-44ff-a58b-2401cfba8f2f",
      "name":"helloProcess",
      "description":"",
      "defaultWorkingDir":"${p:resource\/work.dir}\/${p:component.name}",
      "takesVersion":true,
      "inventoryActionType":"ADD",
      "status":"Active",
      "active":true,
      "versionCount":1,
      "version":1,
      "commit":0,
      "path":"components\/cf355787-a772-4533-be45-3e169e9da6eb\/processes\/12f65517-5fc1-44ff-a58b-2401cfba8f2f"
    }
    ```

3.  Create an application, and then associate the component with the application. 
    1.  Use the createApplication PUT command to create an application.

        ```
        curl -k -u nsmith:passwd
          https://server.example.com:8443/cli/application/create
          -X PUT -d @newApplication.json
        ```

        The following JSON file represents the application:

        ```
        {
          "name": "hello Application",
          "description": "",
          "notificationScheme": "None",
          "enforceCompleteSnapshots": "false"
        }
        ```

        The command returns a result that is similar to the following JSON information:

        ```
        {
          "id":"932452cc-3562-4545-8de5-c57aa7efbcc4",
          "securityResourceId":"2bc72218-dbfe-4c11-b16f-752b7ca63d06",
          "name":"hello Application",
          "description":"",
          "created":1396882026943,
          "enforceCompleteSnapshots":false,
          "active":true,
          "tags":[],
          "user":"nsmith"
        }
        ```

    2.  Use the addComponentToApp PUT command to associate the component with the application.

        ```
        curl -k -u nsmith:passwd 
          "https://server.example.com:8443/cli/
          application/addComponentToApp?component=helloWorld&application=hello%20Application"
          -X PUT
        ```

        The command returns the following result:

        ```
        {}
        ```

4.  Create an environment, and associate it with a resource. 
    1.  Use the createEnvironment PUT command to create an environment.

        ```
        curl -k -u nsmith:passwd 
          "https://server.example.com:8443/cli/environment/createEnvironment?application=hello%20Application&name=helloDeploy"
          -X PUT
        ```

        The command returns the ID of the environment, which is similar to the following string:

        ```
        2142c0e3-7ebe-4a2f-9e0d-14ccacc70a79
        ```

    2.  Use the addEnvironmentBaseResources PUT command to associate the resource that you configured earlier with the environment.

        ```
        curl -k -u nsmith:passwd 
          "https://server.example.com:8443/cli/environment/addBaseResource?application=hello%20Application&environment=helloDeploy&resource=%2FhelloWorld%20Tutorial"
          -X PUT
        ```

        This command does not return a result if the resource is correctly associated with the environment.

    3.  Use the createResource PUT command to map the helloWorld component to the agent resource.

        ```
        curl -k -u nsmith:passwd 
          https://server.example.com:8443/cli/resource/resource 
          -X PUT -d @componentResource.json
        ```

        The following JSON file represents the component resource:

        ```
        {
          "roleId":"09456abd-65e3-469e-94c6-a6a873b971a8",
          "name":"helloWorld",
          "description":"",
          "inheritTeam":"true",
          "useImpersonation":"false",
          "roleProperties":{},
          "parentId":"b2ff919e-b4c0-4d13-8973-eff44e4835e2",
          "teamMappings":[]
        }
        ```

        The command returns a result that is similar to the following JSON information:

        ```
        {
          "id":"ba958487-fb86-4290-9240-da766af37963",
          "securityResourceId":"66685b67-21ab-411d-99bb-f577a74d88b3",
          "name":"helloWorld",
          "path":"\/helloWorld Tutorial\/fit-vm11-157\/helloWorld",
          "active":true,
          "description":"",
          "inheritTeam":true,
          "impersonationPassword":"****",
          "impersonationUseSudo":false,
          "impersonationForce":false,
          "type":"subresource",
          "status":"ONLINE",
          "hasAgent":true,
          "tags":[]
        }
        ```

    4.  Use the addTagToResource PUT command to add a tag to the component resource.

        ```
        curl -k -u nsmith:passwd
          "https://server.example.com:8443/cli/
          resource/tag?resource=ba958487-fb86-4290-9240-da766af37963&tag=blueCycle&color=0000FF"
          -X PUT
        ```

        This command does not return a result if the component is correctly tagged.

5.  Use the createApplicationProcess PUT command to create an application process.

    ```
    curl -k -u nsmith:passwd
      https://server.example.com:8443/cli/application/create
      -X PUT -d @applicationProcess.json
    ```

    The following JSON file represents the application process. The application ID is the same as the ID that is returned in step 3.

    ```
    {
      "application": "932452cc-3562-4545-8de5-c57aa7efbcc4",
      "description": "",
      "inventoryManagementType": "AUTOMATIC",
      "name": "hello App Process",
      "offlineAgentHandling": "PRE_EXECUTION_CHECK",
      "rootActivity": {
        "children": [
          {
            "children": [{
              "children": [{
                "allowFailure": false,
                "children": [],
                "componentName": "helloWorld",
                "componentProcessName": "helloProcess",
                "name": "Deploy helloWorld",
                "properties": {},
                "type": "componentProcess"
              }],
              "componentName": "helloWorld",
              "name": "inventoryVersionCheck",
              "status": "Active",
              "type": "inventoryVersionDiff"
            }],
            "componentName": "helloWorld",
            "failFast": "false",
            "maxIteration": "-1",
            "name": "Deploy helloWorld",
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
            "to": "Deploy helloWorld",
            "type": "ALWAYS",
            "value": ""
          },
          {
            "from": "Deploy helloWorld",
            "to": "FINISH",
            "type": "ALWAYS",
            "value": ""
          }
        ],
        "name": "GRAPH",
        "offsets": [
          {
            "name": "Deploy helloWorld",
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
        "type": "graph"
      }
    }
    ```

    The command returns a result that is similar to the following JSON information:

    ```
    {
      "id":"37d563ce-7885-48f1-b8c0-f79046c0f024",
      "name":"hello App Process",
      "description":"",
      "active":true,
      "inventoryManagementType":"AUTOMATIC",
      "offlineAgentHandling":"PRE_EXECUTION_CHECK",
      "versionCount":1,
      "version":1,
      "commit":0,
      "path":"applications\/932452cc-3562-4545-8de5-c57aa7efbcc4\/processes\/37d563ce-7885-48f1-b8c0-f79046c0f024"
    }
    ```

6.  Use the requestApplicationProcess PUT command to deploy the application.

    ```
    curl -k -u nsmith:passwd
      https://server.example.com:8443/cli/applicationProcessRequest/request
      -X PUT -d @applicationDeploy.json
    ```

    The following JSON file represents the deployment request:

    ```
    {
      "application": "hello Application",
      "applicationProcess": "hello App Process",
      "environment": "helloDeploy",
      "versions": [{
        "version": "1.0",
        "component": "helloWorld"
      }]
    }
    ```

    The command returns a result that is similar to the following JSON information:

    ```
    {"requestId":"bffff82f-ff69-4c07-b010-26ca3f21be39"}
    ```


**Parent topic:** [REST API reference](../../com.ibm.udeploy.reference.doc/topics/rest_api_ref_overview.md)

