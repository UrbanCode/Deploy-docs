# Get information about a resource

This command returns a JSON representation of a resource, including its security settings.

## Request

```
GET https://{hostname}:{port}
    /cli/resource/info?{parameters}
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |

## Example response

```
{
  "id": "e7a3eb3c-a0b2-49d3-80ae-ce788edb101f",
  "name": "My resource",
  "path": "/My resource",
  "active": true,
  "description": "New resource for command example(String)",
  "inheritTeam": false,
  "impersonationPassword": "****",
  "impersonationUseSudo": false,
  "impersonationForce": false,
  "hasAgent": false,
  "tags": [
  ],
  "security": {
    "read": true,
    "write": true
  },
  "propSheet": {
    "id": "b00c0b1c-d007-4c19-a9dd-2e1397df8f1f",
    "name": "custom",
    "path": "resources/e7a3eb3c-a0b2-49d3-80ae-ce788edb101f/propSheetGroup/propSheets/b00c0b1c-d007-4c19-a9dd-2e1397df8f1f",
    "version": 3,
    "versionCount": 3,
    "commit": 111,
    "versioned": true
  },
  "extendedSecurity": {
    "read": true,
    "write": true,
    "Create Resources": true,
    "Edit Resources": true,
    "View Resources": true,
    "teams": [
    ]
  }
}
```

Related CLI command: [getResource](udclient_getresource.md).

**Parent topic:** [resource resource](../../com.udeploy.api.doc/topics/rest_cli_resource.md)

