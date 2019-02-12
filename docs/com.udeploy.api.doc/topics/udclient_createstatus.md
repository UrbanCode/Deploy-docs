# createStatus

Create a status

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  createStatus [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|type|string|true|Type of status \(inventory, version, or snapshot\)|
|status|string|true|Name of the new status|
|color|string|false|Color of the new status \(HTML color strings or valid color names\) \(Optional\)|
|description|string|false|Description of the new status \(Optional\)|
|unique|string|false|Specify true to make this status unique \(Optional\)|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createStatus
  -type version
  -status Documented
  -color "#0077FF"
```

## Example response

```
{
  "id": "abff7bb6-bf95-417e-bf00-b0a8678e832a",
  "type": "VERSION",
  "name": "Documented",
  "active": true,
  "color": "#0077FF",
  "unique": false
}
```

Related REST command: [Create a status](rest_cli_status_createstatus_post.md).

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

