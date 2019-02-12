# Clone a remote blueprint repository

This command clones a remote Git blueprint repository into the server so you can work with those blueprints.

## Request

```
POST http://{hostname}:{port}
  /landscaper/rest/repository/clone
Accept: application/json
Content-Type: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Content-Type|`application/json`|true| |
|Accept|`application/json`|true| |

**Parent topic:** [rest/repository resource](../../com.edt.api.doc/topics/rest_repository_.md)

