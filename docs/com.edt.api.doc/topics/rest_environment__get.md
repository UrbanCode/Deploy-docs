# List environments

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|showAll|string|false| |

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/environment/
```

## Example response

```
[
  {
    "id": "32019dda-4da5-40b1-804b-307a9a2eeb44",
    "name": "Environment1",
    "blueprintName": "MyBlueprint1",
    "blueprintUrl": "https://myserver.example.com:8444/landscaper/view/projects?open=jsmith_
    00000000_0000_0000_0000_000000000002-OrionContent/Internal-Team/MyBlueprint1/MyBlueprint1.yml",
    "stack_status": "CREATE_IN_PROGRESS",
    "stack_status_reason": "Stack CREATE started",
    "creation_time": "2016-01-05T20:58:31Z",
    "owner": "jsmith",
    "regionName": "us-east",
    "cloudProjectName": "MyCloudProject",
    "blueprintOrder": 0
  },
  {
    "id": "32019dda-4da5-40b1-804b-307a9a2eeb44",
    "name": "Environment2",
    "blueprintName": "MyBlueprint2",
    "blueprintUrl": "https://myserver.example.com:8444/landscaper/view/projects?open=jsmith_
    00000000_0000_0000_0000_000000000002-OrionContent/Internal-Team/MyBlueprint1/MyBlueprint2.yml",
    "stack_status": "CREATE_COMPLETE",
    "stack_status_reason": "Stack CREATE completed successfully",
    "creation_time": "2016-01-05T20:30:57Z",
    "owner": "jsmith",
    "regionName": "us-east",
    "cloudProjectName": "MyCloudProject",
    "blueprintOrder": 0
  }
]

```

**Parent topic:** [rest/environment resource](../../com.edt.api.doc/topics/rest_environment_.md)

