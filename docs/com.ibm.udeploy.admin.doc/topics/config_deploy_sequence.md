# Configuring deployment sequence settings

You can configure the blueprint design server to use a list format instead of a tree format for deployment sequences.

In the blueprint designer, by default you edit deployment sequences in a tree format. You can configure the product to use the previous deployment sequence format, which is a sequential list.

1.   In the blueprint designer, open the config.properties file for editing. By default, the config.properties file is stored in the /opt/ibm-ucd-patterns/conf/server/config.properties directory.
2.  Add the following line to the config.properties file. 

    ```
    feature.componentDepencyDialog=simple
    ```

3.  Save the config.properties file, and then restart the Tomcat server. For instructions on stopping and starting the Tomcat server, see [Upgrading the server in interactive mode](../../com.ibm.udeploy.install.doc/topics/upgrade_server.md#).

Now the **Deployment Sequence** resource can be used to create a sequential list of components to deploy, instead of a tree.

**Parent topic:** [Blueprint design server configuration](../../com.ibm.edt.doc/topics/c_node_administering_bds.md)

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

