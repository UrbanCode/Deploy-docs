# List the storage volumes in an environment

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/environment/{environmentId}/volumes
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentId|string|true|ID of the environment|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/environment/32019dda-4da5-40b1-804b-307a9a2eeb44/volumes
```

**Parent topic:** [rest/environment resource](../../com.ibm.edt.api.doc/topics/rest_environment_.md)

