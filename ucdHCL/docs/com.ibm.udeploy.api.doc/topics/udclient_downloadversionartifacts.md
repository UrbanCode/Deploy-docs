# downloadVersionArtifacts

Download the artifacts of a component version

This command exports the artifacts of a component version into an archive file.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  downloadVersionArtifacts [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|component|string|false|Name or ID of the component; this value is required if you specify the version name instead of ID|
|version|string|true|Name or ID of the version|
|location|string|true|Path to download the artifacts to. You must have permission to create files in this location.|
|singleFilePath|string|false|Optional path to an individual version artifact to download. If specified, only that file will be downloaded.|
|encoding|string|false|Optional character encoding to determine the file names of the artifacts. Defaults to the encoding of the file system.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  downloadVersionArtifacts
  -component JPetStore-WEB
  -version 1.0
  -location .
```

Related REST command: [Download the artifacts of a component version](rest_cli_version_downloadartifacts_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

