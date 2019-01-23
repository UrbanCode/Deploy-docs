# Modeling environments for OpenStack and OpenStack-based clouds

To model an OpenStack environment, log in with an OpenStack cloud project and use resources from your cloud system in a blueprint.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).
3.   In the blueprint source code, in the `metadata` property for the resource, specify any virtual image metadata. You provide the metadata as a series of name-value pairs. For example, to specify the tags `cluster: blue` and `database_type: mysql`, the code looks like the following example:

    ```
    metadata:
      cluster: blue
      database_type: mysql
    ```

4.  Create a configuration file and externalize properties to the file.See [Editing configuration files](blueprint_configs.md).

Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

