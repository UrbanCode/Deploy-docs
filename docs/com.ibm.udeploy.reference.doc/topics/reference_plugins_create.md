# Creating plug-ins

You can create your own plug-ins for use with HCL® UrbanCode™ Deploy. A plug-in consists of XML files and supporting script files that the plug-in requires.

-   The plugin.xml file defines the steps that constitute the plug-in; plug-in steps define a plug-in's functions. Each step is an independently configurable entity in the HCL UrbanCode Deploy editor.
-   The info.xml file contains a version ID and other information that describes the plug-in.

**Note:** The plug-in files must use UTF-8 encoding.

A plug-in step is defined by a `<step-type>` element that contains these elements:

-   One `<properties>` element
-   One `<command>` element
-   One `<post-processing>` element

The `<properties>` element is a container for `<property>` child elements, and can contain any number of `<property>` elements. Property values can be specified at design time or run time. The `<post-processing>` element provides error-handling capabilities and sets property values that other steps can use. The `<command>` element runs the step's function. The function can be defined completely by the element or be constructed in part or entirely from the step's properties at design time or run time.

A command can access these properties:

-   The step's own properties
-   Properties that were set earlier by other steps in the process
-   Properties that were set by the application that started the process
-   Properties on the target environment and resource

Step property values become unavailable after the component process ends.

Plug-in steps are run by an agent that is installed in the target environment. Thus, plug-ins can be written in any scripting language, and the agent can access the required scripting tools on the host. After a plug-in is created, upload it into HCL UrbanCode Deploy to make it available to users. To upload a plug-in, create an archive file that contains the XML files \(plugin.xml and info.xml\) and scripts that the plug-in requires. Then, import the archive file with the Automation Plugins pane for automation-type plug-ins or the Source Config Plugins pane for source plug-ins.

To troubleshoot plug-ins, you can retrieve the information from each step that ran in a process request. To download these logs, open the process request and click **Download All Logs**.

See [UrbanCode Deploy Plug-in for Eclipse Development](http://hub.jazz.net/project/ucplugin/UrbanCode%20Deploy%20Plug-in%20For%20Eclipse%20Development/overview) in the [IBM® Bluemix® DevOps Services](http://hub.jazz.net) community for a tool that can you save time in developing plug-ins.

-   **[The plugin.xml file for automation plug-ins](../../com.ibm.udeploy.reference.doc/topics/ref_create_pluginxml.md)**  
An automation plug-in is defined with the plugin.xml file.
-   **[Creating source plug-ins](../../com.ibm.udeploy.reference.doc/topics/ref_create_pluginsrc.md)**  
Source-type plug-ins are defined the same way that automation-type plug-ins are defined except for some modifications to the plugin.xml file.
-   **[Plug-in steps: The step-type element](../../com.ibm.udeploy.reference.doc/topics/ref_create_steptype.md)**  
You define plug-in steps with the `step-type` element; each `step-type` element represents a single step in the HCL UrbanCode Deploy process editor.
-   **[The command element](../../com.ibm.udeploy.reference.doc/topics/ref_create_command.md)**  
Steps are run by starting the scripting tool or interpreter that is specified by the `<command>` element. The `<command>` element's `program` attribute defines the location of the tool that runs the command.
-   **[The post-processing element](../../com.ibm.udeploy.reference.doc/topics/ref_create_postprocessing.md)**  
When a plug-in step's `<command>` element finishes processing, the step's mandatory `<post-processing>` element runs.
-   **[Upgrading plug-ins](../../com.ibm.udeploy.reference.doc/topics/ref_create_upgrading.md)**  
This example shows how to upgrade a plug-in.
-   **[The info.xml file](../../com.ibm.udeploy.reference.doc/topics/ref_create_infoxml.md)**  
Use the info.xml file is required for each plug-in. It describes the plug-in and provides release notes to users for each version.
-   **[Automatically importing objects from plug-ins](../../com.ibm.udeploy.reference.doc/topics/ref_import_obj.md)**  
You can add objects to plug-ins so that they are automatically imported when the plug-in is installed or upgraded. Objects include applications, components, component templates, and processes. For example, you can add a component template that implements a standard process to a plug-in, so that the plug-in user does not have to create the component template.

**Parent topic:** [Plug-ins](../../com.ibm.udeploy.reference.doc/topics/plugin_ch.md)

