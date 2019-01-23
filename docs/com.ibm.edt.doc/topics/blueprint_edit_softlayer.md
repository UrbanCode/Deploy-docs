# Modeling environments for SoftLayer

To model a SoftLayer® environment, log in with a SoftLayer cloud project and specify the information that is specific to SoftLayer in a blueprint.

-   Configure the images for use with the blueprint designer. See [Configuring private SoftLayer images](cloud_connect_softlayer_images.md).
-   On the SoftLayer web portal, create an object storage account.
-   Connect to SoftLayer. See [Connecting to the SoftLayer cloud](cloud_connect_softlayer.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).
3.   Specify how to install the HCL® UrbanCode™ Deploy agent: 
    -   By default, public images use the SoftLayer storage account to install the HCL UrbanCode Deploy agent. A script in the storage account installs the HCL UrbanCode Deploy agent when you provision an image.
    -   By default, private \(custom\) images use the `cloud-init` package to install the HCL UrbanCode Deploy agent.
    -   To use the storage account to install the agent on a private image, set the use\_cloudinit property to false, as shown in the following code:

        ```
        image_A:
          type: OS::Nova::Server
          properties:
            name: "My image A"
            image: "MyImage123"
          metadata:**
            softlayer\_properties:
              storage\_account: \{ get\_param: storage\_account \}
              storage\_datacenter: \{ get\_param: storage\_datacenter \}
              use\_cloudinit: false**
        ```

4.  If you host your engine in a private SoftLayer network and provision images to that private network, set the storage\_private\_url to `true`, as shown in the following code: 

    ```
    image_A:
      type: OS::Nova::Server
      properties:
        name: "My image A"
        image: "MyImage123"
      metadata:
    **    softlayer\_properties:
          storage\_private\_url: true**
    ```

5.   In the blueprint source code, in the `metadata` property for the resource, specify any virtual image tags. To parametrize the data, you can specify a list of values. You can also specify a series of comma-separated strings. For example, to specify the parameterized tags `blue` and `mysql_database`, the code looks like the following example:

    ```
    
    resources:
      myImageType:
        type: OS::Nova::Server
        properties:
          name: myImageType
          image: myImageName
          flavor: {get_param: flavor}
          key_name: {get_param: key_name}
        **metadata:
          tags: \['blue', 'mysql\_database'\]**
    ```

    If you do not plan to reuse the tags as parameters, the code looks like the following example:

    ```
    resources:
      myImageType:
        type: OS::Nova::Server
        properties:
          name: myImageType
          image: myImageName
          flavor: {get_param: flavor}
          key_name: {get_param: key_name}
        **metadata:
          tags: blue, mysql\_database**
    ```

6.  Create a configuration file, and externalize properties to the file.See [Editing configuration files](blueprint_configs.md).
7.  In the configuration file, ensure that the core OpenStack types are mapped to SoftLayer types. The configuration file must have mapping that is similar to this code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::SoftLayer::Server
    
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

