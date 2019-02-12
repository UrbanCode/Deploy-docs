# getResource

Get information about a resource

This command returns a JSON representation of a resource, including its security settings.

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  getResource [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|resource|string|true|Path to the resource, such as /ResourceGroup/Agents/Agent1|
|template|string|false|Name or ID of the resource template \(Optional\)|
|blueprintId|string|false|Name or ID of the blueprint \(Optional\)|
|application|string|false|Name or ID of the application \(Required to look up blueprint by name\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getResource
  -resource "/My resource"
```

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

Related REST command: [Get information about a resource](rest_cli_resource_info_get.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

