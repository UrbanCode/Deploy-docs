# List resources that have a specified component version

This command returns a JSONArray representation of all resources that have the specified component version installed.

## Request

```
GET https://{hostname}:{port}
    /cli/resource/withVersion?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|version|string|true|Version name|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
[
  {
    "id": "53b4b54f-5b3f-4fef-91dd-dea8ffe15dc3",
    "name": "JPetStore-APP",
    "path": "/JPetStore agents/vm192-168/JPetStore-APP",
    "active": true,
    "description": "",
    "inheritTeam": true,
    "impersonationPassword": "****",
    "impersonationUseSudo": false,
    "impersonationForce": false,
    "type": "subresource",
    "status": "ONLINE",
    "hasAgent": true,
    "tags": [
    ]
  }
]
```

Related CLI command: [getResourcesWithComponentVersion](udclient_getresourceswithcomponentversion.md).

**Parent topic:** [resource resource](../../com.udeploy.api.doc/topics/rest_cli_resource.md)

