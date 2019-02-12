# Integrating with Chef

Chef can automate infrastructure tasks, such as installing databases and application servers. By integrating the blueprint designer with Chef, you can apply Chef roles to images in blueprints. When you provision environments, the environments run the Chef automation scripts that are based on those roles.

**Note:** These instructions are for using Chef when you provision environments on cloud systems via OpenStack Heat. To use Chef in component processes, see the [Chef automation plugin](https://developer.ibm.com/urbancode/plugin/chef/).

-   Chef roles are supported on only OpenStack, VMware, and SoftLayer® clouds.
-   To use Chef, you must have a Chef server that contains roles and cookbooks. For information about setting up Chef, see [https://www.chef.io](https://www.chef.io). The Chef server must have at least one Chef environment, which is not to be confused with cloud environments. By default, Chef servers have an environment that is named `_default`.

To use Chef roles in blueprints, you must connect to a Chef server. Then, you configure the target images to use Chef roles. Then, you can add Chef roles to images in blueprints.

1.   Log in to the blueprint designer as an administrator. 
2.  Click **Settings** \> **System Settings**.
3.  In the **Chef Server** section, specify the following information.If you don't see this section, open the config.properties file on the computer that hosts the blueprint design server, set the com.ibm.ucd-patterns.feature.chef-server property to `true`, and restart the blueprint design server.

    -   ****Chef Server URL****

        The URL of the Chef server, such as `https://chef.example.com:443/organizations/myogranization`.

    -   ****Chef Validator Name****

        The name of the validator that clients use to connect to the Chef server.

    -   ****Chef Validator Key****

        The name of the key for the validator. Paste the content from the validator key file that is in the chef-starter.zip file \(starter kit\).

    -   ****Chef Client Name****

        The name of a Chef user that has access to the Chef server.

    -   ****Chef Client Key****

        The key for the client. Paste the content from the client key file that is in the chef-starter.zip file \(starter kit\).

    **Note:** If you used Chef in versions of the blueprint designer before 6.2.1 and upgraded to version 6.2.1 or later, the value that you provided for the **Chef Validator Key URL** cannot be modified. To use a different validator key, before you provision an environment that contains Chef roles, you must modify the blueprint. See [Modifying blueprints to access the Chef validator key in version 6.2.1 and later](chef_validator.md#).

4.   Click **Save**. 
5.   To connect to the Chef server via SSL, see [Configuring SSL/TLS security for Chef](integrate_chef_ssl.md). 
6.   If you use a Kilo, Liberty, or Mitaka level Heat engine that you extended, modify the engine to be compatible with Chef. On the system that hosts the Heat engine, run the following command:

    ```
    sed -i '125,127 s/^/#/' /usr/lib/python2.7/site-packages/heat/engine/resources/openstack/heat/software_deployment.py
    sed -n '125,127p' /usr/lib/python2.7/site-packages/heat/engine/resources/openstack/heat/software_deployment.py
    ```

    The following text is displayed in the command line:

    ```
    # constraints=[#
        constraints.CustomConstraint('nova.server')# ]
    ```


Configure the virtual images for Chef. See [Creating Chef-compatible images](integrate_chef_images.md).

-   **[Creating Chef-compatible images](../../com.edt.doc/topics/integrate_chef_images.md)**  
To use images with Chef and the blueprint designer, you must create the images with certain prerequisites.
-   **[Updating Chef-compatible images](../../com.edt.doc/topics/cloud_update_chef_images.md)**  
If your image uses Chef recipes, after you upgrade to HCL® UrbanCode™ Deploy version 6.2.1 or later, you must manually update the Chef hook on the images in your cloud.
-   **[Configuring SSL/TLS security for Chef](../../com.edt.doc/topics/integrate_chef_ssl.md)**  
If your Chef server uses SSL/TLS security, you must import the Chef server key into the blueprint design server keystore.

**Parent topic:** [Overview of integrations](../../com.udeploy.doc/topics/integrat_ov.md)

