# List the availability zones on a cloud

This command lists the availability zones on the appropriate cloud for a specified configuration file.

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resources/availabilityZones/blueprint/{blueprint}/configuration/{configuration}
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
  http://myserver.example.com:8080/landscaper/rest/cloud/avaiabilityZones/
  blueprint/My_Blueprint/configuration/MyConfig1
  -H "Accept: application/json"
```

## Example response

```
[
  {
    "name": "zone A",
    "id": "a"
  },
  {
    "name": "zone B",
    "id": "b"
  }
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

