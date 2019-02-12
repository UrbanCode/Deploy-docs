# List the floating IP addresses for a cloud type

This command lists the floating IP addresses on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/floatingIPs/blueprint/{blueprint}/configuration/{configuration}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|blueprint|string|true|The blueprint ID|
|configuration|string|true|The configuration file ID|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resources/
  floatingIPs/blueprint/MyBlueprint/configuration/MyConfigOpenStack
```

## Example response

```
[
    {
        "id": "34f0efe0-05d9-420c-922b-883d5b06cafa",
        "name": "10.10.164.37"
    },
    {
        "id": "1ef7858e-66c7-547c-824b-38faa1b2be8f",
        "name": "10.10.164.60"
    }]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

