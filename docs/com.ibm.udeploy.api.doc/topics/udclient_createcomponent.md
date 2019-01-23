# createComponent

Create a component

## Format

```
udclient [\[global-args...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md) [\[global-flags...\]](../../com.ibm.udeploy.reference.doc/topics/cli_command_format.md)
  createComponent [JSON file]
```

## Parameters

None.

## Template

This command takes a JSON request string or file. Use the following template for the request:

```
{
  "cleanupCountToKeep": "Number of most recent versions to 
  keep; omit this parameter to inherit the system settings 
  (Optional)",
  "cleanupDaysToKeep": "Number of days to keep versions; 
  omit this parameter to inherit the system settings 
  (Optional)",
  "defaultVersionType": "The default type to create 
  versions with; valid values are FULL and INCREMENTAL",
  "description": "Description",
  "importAutomatically": "Specify true to import new 
  versions automatically",
  "integrationAgent": "ID of the Agent for importing new 
  component versions (Optional)",
  "integrationTag": "Name of existing tag to use 
  (Optional)",
  "name": "Component name or ID",
  "properties": {"Source configuration plugin property 
  name": "Property value"},
  "sourceConfigPlugin": "The name of the source 
  configuration plug-in to use; this property is required 
  even if you are creating the component from a template",
  "teamMappings": [{
    "resourceRoleId": "Id of Resource Type to apply to 
  this team mapping (optional, can specify either this or 
  resourceRoleLabel",
    "resourceRoleLabel": "Name of Resource Type to apply 
  to this team mapping (optional, can specify either this or 
  resourceRoleId",
    "teamId": "ID of a team, either this field or 
  teamLabel are needed to specify a team",
    "teamLabel": "Name of the team to map the environment 
  to, either this field or teamId are needed to specify a 
  team"
  }],
  "templateId": "ID of the template to use (Optional)",
  "templateName": "Name of a template to use; this 
  parameter is ignored if  templateId is specified 
  (Optional)",
  "templateVersion": "Version number of the specified 
  template (Optional)",
  "useVfs": "Boolean"
}

```

## Example

```
udclient -username jsmith -password passwd 
  -weburl https://myserver.example.com:8443
  createComponent newComponent.json

```

## Example JSON requests

```
{
  "name": "My new component",
  "description": "New component for command example",
  "importAutomatically": false,
  "useVfs": true,
  "sourceConfigPlugin": "File System (Versioned)",
  "defaultVersionType": "FULL",
  "properties": {
    "FileSystemVersionedComponentProperties\/basePath": 
    "/opt/newcomponent"
  }
}
```

The properties attribute in the JSON template refers to properties for the source configuration plug-in, not custom properties. For example, the following code creates a component from a Maven repository. It includes properties that are prefixed with `MavenComponentProperties` to refer to the properties for that plug-in.

```
{
  "name": "Component from Maven",
  "description": "New component for command example for Maven",
  "importAutomatically": false,
  "useVfs": false,
  "sourceConfigPlugin": "Maven",
  "defaultVersionType": "FULL",
  "properties": {
    "MavenComponentProperties\/artifactId":"MyArtifact",
    "MavenComponentProperties\/groupId":"MyGroup",
    "MavenComponentProperties\/extension":"ext",
    "MavenComponentProperties\/repoUrl":"http:\/\/myserver.com"
  }
}
```

To see the properties for a source configuration plug-in, create a component in the web interface and use the source configuration plug-in. Then, then export its information with the [getComponent](udclient_getcomponent.md) command. The JSON that this command returns includes the properties for the source configuration plug-in. You can also look in the plugin.xml file in the plug-in.

To create a component from a template, specify either the templateId attribute or the templateName attribute. Then, specify the templateVersion attribute; to use the most recent version of the template, specify an empty string. If the template contains property definitions, you can specify values for those properties with the attribute `template/propertyName`, where `propertyName` is the name of the property. For example, the following JSON code creates a component from the most recent version of the Template1 template. This code specifies the value `MyValue` for the parameter template/MyProperty.

```
{
  "name":"NewComponent1", 
  "description":"",
  **"templateName":"Template1", 
  "templateVersion":"",
  "template/MyProperty":"MyValue",** 
  "componentType":"STANDARD", 
  "sourceConfigPlugin":"",
  "importAutomatically":"false", 
  "useVfs":"true",
  "defaultVersionType":"FULL", 
  "importAgentType":"inherit",
  "inheritSystemCleanup":"true",
  "runVersionCreationProcess":"false",
  "properties":{},
  "teamMappings":[]
}
```

## Example response

```
{
  "id": "e84c7947-fad1-4399-8eb8-0d0d354b9e2b",
  "name": "My new component",
  "description": "New component for command example",
  "created": 1391456765556,
  "importAutomatically": false,
  "useVfs": true,
  "active": true,
  "deleted": false,
  "defaultVersionType": "FULL",
  "cleanupDaysToKeep": 0,
  "cleanupCountToKeep": 0,
  "tags": [
  ],
  "user": "admin"
}
```

## Team mappings

When creating UrbanCode Deploy objects from the CLI we pass in JSON payloads that set the configuration.

These JSON files can include a "teamMappings" attribute that looks like this:

```
"teamMapping":[ 
{ 
"teamId" : "TEAM UIID", "teamLabel": "TEAM NAME", (can specify teamId or teamLabel), 
"resourceRoleId": "ResRole UUID", "resourceRoleLabel":"Name of Resource Role" (can specify this or resRoleId) }
,
{ "teamId" : "TEAM UIID2", "teamLabel": "TEAM NAME2", (can specify teamId or teamLabel), 
"resourceRoleId": "ResRole UUID2", "resourceRoleLabel":"Name of Resource Role2" (can specify this or resRoleId) }
,
{MORE TEAM MAPPINGS}
]
```

Related REST command: [Create a component](rest_cli_component_create_put.md).

**Parent topic:** [CLI Commands](../../com.ibm.udeploy.reference.doc/topics/cli_commands.md)

