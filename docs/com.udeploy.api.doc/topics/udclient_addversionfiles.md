# addVersionFiles

Upload files to a version

## Format

```
udclient [\[global-args...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.udeploy.reference.doc/topics/cli_command_format.md)
  addVersionFiles [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name/ID of the component \(Only required if not using version ID\)|
|version|string|true|Name/ID of the version|
|base|string|true|Local base directory for upload. All files inside this will be sent.|
|offset|string|false|Target path offset \(the directory in the version files to which these files should be added\)|
|include|string|false|An include file pattern for selecting files to add \(may be repeated\)|
|exclude|string|false|An exclude file pattern for excluding files \(may be repeated\). Overrides includes.|
|saveExecuteBits|boolean|false|Saves execute bits for files.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  addVersionFiles
  -component JPetStore-WEB
  -version 1.1
  -base newImageFolder
```

**Parent topic:** [CLI Commands](../../com.udeploy.reference.doc/topics/cli_commands.md)

