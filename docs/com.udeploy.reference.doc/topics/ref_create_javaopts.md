# The plugin-javaopts.conf file

The plugin-javaopts.conf file can be used to set the JAVA\_OPTS environment variable for automation plug-ins that use Groovy.

By default, the plugin-javaopts.conf file is stored on the agent computer in the agent\_installation\_directory/conf/ folder. You can use the plugin-javaopts.conf file to set the JAVA\_OPTS environment variable for a plug-in that is different from the JAVA\_OPTS variable for the agent process itself. The plug-in must use Groovy, and not Java™.

**Note:** If there are syntax errors in the plugin-javaopts.conf file, errors and unpredictable behavior can result. Also, any custom modifications that you make to the plugin-javaopts.conf file might be overwritten if you upgrade the agent to a newer version.

If you use the IBM Java Runtime Environment \(JRE\) to run the agent, you might achieve faster step execution times by adding the -Xquickstart parameter to the plugin-javaopts.conf file. For information about this parameter, see [https://www.ibm.com/support/knowledgecenter/SSYKE2\_8.0.0/com.ibm.java.zos.80.doc/diag/appendixes/cmdline/xquickstart.html](https://www.ibm.com/support/knowledgecenter/SSYKE2_8.0.0/com.ibm.java.zos.80.doc/diag/appendixes/cmdline/xquickstart.html).

**Important:** Only use the -Xquickstart parameter with the IBM JVM. Do not use this parameter with the Oracle JDK or Open JDK distributions.

**Parent topic:** [The plugin.xml file for automation plug-ins](../../com.udeploy.reference.doc/topics/ref_create_pluginxml.md)

