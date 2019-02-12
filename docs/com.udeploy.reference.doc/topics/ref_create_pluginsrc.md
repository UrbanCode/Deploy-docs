# Creating source plug-ins

Source-type plug-ins are defined the same way that automation-type plug-ins are defined except for some modifications to the plugin.xml file.

Like automation plug-ins, source plug-ins are defined with two files, an info.xml file and a plugin.xml file. The structure of the first file is identical for both plug-in types. The structure of the plugin.xml file varies depending on the type of plug-in. For information about the plugin.xml file for automation plug-ins, see [The plugin.xml file for automation plug-ins](ref_create_pluginxml.md#).

The following code fragment is an example of a source plug-in file. The `<server:plugin-type>Source</server:plugin-type>` tag identifies the type of plug-in. For source plug-ins, the type must be `Source`:

```
<?xml version="1.0" encoding="UTF-8"?>
<!-- the xmlns:server argument is necessary to parse the tags with the server prefix -->
<plugin xmlns="http://www.urbancode.com/PluginXMLSchema_v1" 
    xmlns:server="http://www.urbancode.com/PluginServerXMLSchema_v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
  <header>
    <identifier id="com.urbancode.air.plugin.source.Name" name="Plugin Name" version="1"/>
    <description>Short description</description>
    <tag>SCM/Name</tag>
    
   ** <server:plugin-type\>Source</server:plugin-type\>**
  </header>

   
```

A source plug-in has one step, which must be named `Import Version`:

```


    ** <step-type name="Import Version"\>**
      <description>Creates a new component version and imports artifacts</description>
      <properties>
      </properties>
      <post-processing><![CDATA[
        if (properties.get("exitCode") != 0) {
            properties.put(new java.lang.String("Status"), new java.lang.String("Failure"));
        }
        else {
            properties.put("Status", "Success");
        }
     ]]></post-processing>
     
      <command program="${JAVA_HOME}/bin/java">
        <arg value="${JAVA_OPTS}"/>
        <arg value="-jar"/>
        <arg file="FileSystemSourceConfig.jar"/>
        <arg value="ImportVersion"/>
        <arg file="${PLUGIN_INPUT_PROPS}"/>
        <arg file="${PLUGIN_OUTPUT_PROPS}"/>
      </command>
      
    </step-type>
    
   
```

As shown in the following code fragment, source plug-ins have two property groups. `Component` type properties are configured with the Create Component window. `Import` type properties are configured with the Import Component window.

```


       
    <!-- ==================================== -->
    <!--   Properties                         -->
    <!-- ==================================== -->
   
   ** <server:property-group type="Component" name="FileSystemComponentProperties"\>**
      <server:property name="property-name" required="true">
        <server:property-ui type="textBox"
                            label="property-label"
                            description="property-description" />
      </server:property>
    </server:property-group>
    
       <!-- If left empty or omitted then no dialog will appear -->
  **  <server:property-group type="Import" name="FileSystemImportProperties"\>**
      <server:property name="property-name" required="true">
        <server:property-ui type="textBox"
                            label="property-label"
                            description="property-description" />
      </server:property>
    </server:property-group>
</plugin>
```

**Parent topic:** [Creating plug-ins](../../com.udeploy.reference.doc/topics/reference_plugins_create.md)

