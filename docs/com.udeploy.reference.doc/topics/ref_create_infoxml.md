# The info.xml file

Use the info.xml file is required for each plug-in. It describes the plug-in and provides release notes to users for each version.

The following code is an example of a simple info.xml file.

```
<?xml version="1.0" encoding="UTF-8"?>
<pluginInfo>
  <author name="IBM UrbanCode">
    <organization>IBM UrbanCode</organization>
    <email>ucplugin@us.ibm.com</email>
    <website>https://developer.ibm.com/urbancode/plugins/</website>
    <bio/>
  </author>

  <integration type="Deploy"/>
   
  <source url="https://developer.ibm.com/urbancode/plugins/"/>
  
  <licenses>
    <license type="IBM"/>
  </licenses>

  <tool-description>Sample plug-in for IBM UrbanCode Deploy</tool-description>
  
  <related-info>
    <link description="Documentation for IBM UrbanCode Deploy" 
  title="IBM Knowledge Center" type="WEBSITE" 
  url="http://www-01.ibm.com/support/knowledgecenter/SS4GSP/ucd_welcome.html"/>
  </related-info>
    
  <release-version>12345</release-version>
    
  <release-notes>
      <release-note plugin-version="2">
Fixed some bugs with the plug-in.
      </release-note>
      <release-note plugin-version="1">
Fixed some bugs with the plug-in.
      </release-note>
  </release-notes>
</pluginInfo>
```

This file contains the following sections:

-   **`<author>` \(required\)**

    This section provides information about the author of the plug-in.

-   **`<integration>` \(required\)**

    This tag specifies the general type of plug-in. For source configuration plug-ins, specify `Source`. For plug-ins that retrieve artifacts from a repository during a deployment, specify `Artifact`. For plug-ins that deploy code to a middleware server, specify `Deploy`. For other automation tasks, specify `Automation`.

-   **`<source>`**

    This tag specifies the location of the source code for the plug-in, if that source code is available.

-   **`<licenses>`**

    This tag provides a description of the license for the plug-in.

-   **`<tool-description>`**

    This tag provides information about the software or system that the plug-in integrates with.

-   **`<related-info>`**

    This tag provides related links.

-   **`<meta-html>`**

    This tag provides information about the description of the plug-in on web pages.

-   **`<release-version>`**

    The build version of the plug-in, which is not necessarily the same as the version in the plugin.xml file.

-   **`<release-notes>` \(required\)**

    This section includes release notes for the current and previous versions of the plug-in. These versions must match the version in the plugin.xml file.


**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

