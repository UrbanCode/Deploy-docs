# getResourceTemplateChildren

Get all children or descendants of a resource template

Results include the base resource and resources inherited from ancestors of this template.

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  getResourceTemplateChildren [parameters]
```

## Parameters

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|template|string|true|Name or ID of the resource template. If this is a blueprint identified by name rather than ID, a parent application must also be specified using the -application flag.|
|application|string|false|Name or ID of the parent application. Required if the template represents an application blueprint identified by name.|
|recursive|boolean|false|Get all descendants of the template \(not just immediate children\). Default is false.|

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  getResourceTemplateChildren
  -template MyResourceTemplate
```

Related REST command: [Get all children or descendants of a resource template](rest_cli_resourcetemplate_getchildren_get.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

