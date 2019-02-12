# List all blueprint resources

This command returns a list of blueprints.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/blueprint/resources
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
   -H 'Accept: application/json'
  http://myserver.example.com:8080/landscaper/rest/
  blueprint/resources
```

**Parent topic:** [rest/blueprint resource](../../com.edt.api.doc/topics/rest_blueprint_.md)

