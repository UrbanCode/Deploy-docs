# getResourcesWithComponentVersion

List resources that have a specified component version

This command returns a JSONArray representation of all resources that have the specified component version installed.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getResourcesWithComponentVersion [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|true|Name or ID of the component|
|version|string|true|Version name|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getResourcesWithComponentVersion
  -component "JPetStore-APP"
  -version "1.0"
```

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

Related REST command: [List resources that have a specified component version](rest_cli_resource_withversion_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

