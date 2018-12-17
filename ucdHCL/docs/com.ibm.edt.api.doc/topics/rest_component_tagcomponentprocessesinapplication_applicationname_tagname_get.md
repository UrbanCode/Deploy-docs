# List processes for components with the specified tag

This command lists component processes. You specify an application and a tag and the command returns the processes in components that are both in the application and have the tag.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/tagComponentProcessesInApplication/{applicationName}/{tagName}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|tagName|string|true|The name of the tag|
|applicationName|string|true|The name of the application|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper
  /rest/component/tagComponentProcessesInApplication/MyApplication/MyTag" 
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "id": "b2392c02-1f39-4ae5-b2ad-5100f63d31a8",
    "name": "ComponentProcess1",
    "description": "",
    "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
    "takesVersion": true,
    "inventoryActionType": "ADD",
    "status": "Active",
    "configActionType": "ADD",
    "active": true,
    "versionCount": 1,
    "version": 1,
    "commit": 20,
    "path": "components/fdd64346-7743-4317-97ae-0056a3549882/processes/b2392c02-1f39-4ae5-b2ad-5100f63d31a8"
  },
  {
    "id": "f4bdef2c-e999-4e19-8d6d-1506132b76a0",
    "name": "ComponentProcess2",
    "description": "",
    "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
    "takesVersion": true,
    "inventoryActionType": "ADD",
    "status": "Active",
    "configActionType": "ADD",
    "active": true,
    "versionCount": 1,
    "version": 1,
    "commit": 11,
    "path": "components/c6a8f9b0-54f8-4a09-857e-e15eec6d4eff/processes/f4bdef2c-e999-4e19-8d6d-1506132b76a0"
  },
  {
    "id": "1230d16b-44be-4295-8af7-42690552043d",
    "name": "ComponentProcess3",
    "description": "",
    "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
    "takesVersion": true,
    "inventoryActionType": "ADD",
    "status": "Active",
    "configActionType": "ADD",
    "active": true,
    "versionCount": 1,
    "version": 1,
    "commit": 21,
    "path": "components/fdd64346-7743-4317-97ae-0056a3549882/processes/1230d16b-44be-4295-8af7-42690552043d"
  },
  {
    "id": "a466fa5c-f59c-4251-9700-bd9e988461d8",
    "name": "ComponentProcess4",
    "description": "",
    "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
    "takesVersion": true,
    "inventoryActionType": "ADD",
    "status": "Active",
    "configActionType": "ADD",
    "active": true,
    "versionCount": 1,
    "version": 1,
    "commit": 18,
    "path": "components/c6a8f9b0-54f8-4a09-857e-e15eec6d4eff/processes/a466fa5c-f59c-4251-9700-bd9e988461d8"
  }
]

```

**Parent topic:** [rest/component resource](../../com.ibm.edt.api.doc/topics/rest_component.md)

