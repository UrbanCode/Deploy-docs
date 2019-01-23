# The `header` element

The mandatory `header` element identifies the plug-in and contains three mandatory child elements and one optional child element:

| `<header>` Child Elements|Description|
|--------------------------|-----------|
|`<identifier>` |This element's 3 attributes identify the plug-in: -   `version`

API version \(the version number for upgrading plug-ins is defined in the info.xml file\).

-   `id`

Identifies the plug-in.

-   `name`

The plug-in name is shown on the Automation Plugins pane, and on informational pages for the plug-in.


All values must be enclosed within single quotation marks.|
|`<description>` |Describes the plug-in; is shown on the Automation Plugins pane, and on informational pages for the plug-in.|
|`<tag>` |Defines where the plug-in is listed within the process editor's hierarchy of available plug-ins. The location is defined by a string that is separated by slashes. For example, the Tomcat definition is the following string: `Application Server/Java/Tomcat`. The Tomcat steps are listed beneath the Tomcat item, which in turn is nested within the other two. **Note:** Do not include underscores in this element.

|
|`<server:required-server-version>`|This optional element defines the minimum version of HCL® UrbanCode™ Deploy required for use with the plug-in. The version is defined by 4 digits. For example, a plug-in that requires HCL UrbanCode Deploy Version 6.0.1 or later would include the following element in the header: ```
<server:required-server-version>6.0.1.0</server:required-server-version>
```

|
|`<server:dependencies>`|This optional element specifies other plug-ins that must be loaded before this plug-in. The `<server:dependencies>` element contains a `<server:dependency>` element that specifies the identifier and minimum version for each dependency. For example, a plug-in that requires version 76 or later of the WebSphere® Application Server - Deploy plug-in would include the following elements in the header:```
<server:dependencies>
  <server:dependency plugin-id="com.urbancode.air.plugin.WebSphere" min-version="76"/>
</server:dependencies>
```

|

The following text is a sample header definition:

```
<header>
  <identifier version="3" id="com.&company;.air.plugin.Tomcat" name="Tomcat"/>
  <description>
  The Tomcat plugin is used during deployments to run Tomcat run-book 
  automations and deploy or undeploy Tomcat applications.
  </description>
  <tag>Application Server/Java/Tomcat</tag>
</header>
```

**Parent topic:** [The plugin.xml file for automation plug-ins](../../com.ibm.udeploy.reference.doc/topics/ref_create_pluginxml.md)

