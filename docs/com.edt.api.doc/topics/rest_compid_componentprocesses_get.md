# List the processes for a component

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/component/{componentId}/componentProcesses
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|componentId|string|true|The ID of the component, not the name|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/component/123ABC/componentProcesses
```

## Example response

```
[
    {
        "componentId": "123ABC",
        "componentProcessVersion": 3,
        "defaultWorkingDir": "${p:resource/work.dir}/${p:component.name}",
        "description": "A component process",
        "id": "0d358adc-3458b-4b20-a73f-3203e257b9a1",
        "name": "Deployment process for this component",
        "takesVersion": true
    }
]
```

**Parent topic:** [rest/component resource](../../com.edt.api.doc/topics/rest_component.md)

