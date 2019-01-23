# Delete an environment

## Request

```
DELETE http://{hostname}:{port}
  /landscaper/rest/environment/{environmentName}/{environmentId}

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentName|string|true|Name of the environment|
|environmentId|string|true|ID of the environment|

## Example

```
curl -u jsmith:passwd 
   -X DELETE
  http://myserver.example.com:8080/landscaper/rest/environment/MyEnvironment/32019dda-4da5-40b1-804b-307a9a2eeb44
```

## Example response

**Note:** If the command returns only a response code of 200 and no JSON, the engine successfully deleted the environment.

**Parent topic:** [rest/environment resource](../../com.ibm.edt.api.doc/topics/rest_environment_.md)

