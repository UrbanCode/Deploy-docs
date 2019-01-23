# Get a unique environment name

This command checks that an environment name is not already in use. If the specified name is in use, the command returns a similar unique name.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/{environmentName}/uniqueEnvironmentName/
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|environmentName|string|true|The environment name to check.|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/
  blueprint/myNewEnvironment/uniqueEnvironmentName/
  -H "Accept: application/json"
```

## Example response

```
{"unique":"myNewEnvironment1"}
```

**Parent topic:** [rest/blueprint resource](../../com.ibm.edt.api.doc/topics/rest_blueprint_.md)

