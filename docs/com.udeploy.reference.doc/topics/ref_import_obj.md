# Automatically importing objects from plug-ins

You can add objects to plug-ins so that they are automatically imported when the plug-in is installed or upgraded. Objects include applications, components, component templates, and processes. For example, you can add a component template that implements a standard process to a plug-in, so that the plug-in user does not have to create the component template.

To automatically import objects from plug-ins, place the JSON representation of the object in the plug-in archive file, in the appropriate directory. The JSON files must have the .json extension. For example, if you have an application in a JSON file, the file must be in the imports/applications folder of the archive file.

The following table lists the locations for each object type.

|Object type|Location|
|-----------|--------|
|Applications|imports/applications/|
|Components|imports/components/|
|Component templates|imports/componenttemplates/|
|Processes|imports/processes/|

**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

