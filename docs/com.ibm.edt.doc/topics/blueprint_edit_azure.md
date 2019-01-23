# Modeling environments for Microsoft Azure

To model a Microsoft™ Azure environment, log in with an Azure cloud project and specify the Azure-specific information in a blueprint.

-   Upgrade the blueprint design server and engine to version 6.2.1.1 or later.
-   On the Azure web portal, create a security group for new environments. The security group determines which ports are open on the images, so you must use a security group that has the appropriate ports open for agent communication. See [Firewall and communication configuration](../../com.ibm.udeploy.install.doc/topics/agent_firewalls.md).
-   On the Azure web portal, set up a standard storage account. You can use only standard storage accounts with the blueprint designer.
-   On the Azure web portal, set up a virtual network.
-   On the Azure web portal, organize your artifacts. Place the storage account, virtual network, and any custom images that this blueprint includes in the same resource group.

    **Note:** Blueprints must contain custom images, networks, and storage accounts from the same resource group.

-   Connect the blueprint design server to Azure. See [Connecting to Microsoft Azure](cloud_connect_azure.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

You cannot use SSH keys to secure images on Azure. Only user name and password security is supported.

Beginning with version 6.2.1.1, you can use Windows and Linux images on Azure.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add virtual images from the palette to the blueprint. The images in the palette are a subset of the images in the Azure Virtual Machines Marketplace and custom images that you registered with the cloud discovery service. If you add custom images, you must select images that are part of a single resource group.

    Beginning in version 6.2.1.1, you can specify a custom name for the virtual machine disk with the os\_disk\_name property. If you do not specify this property and a disk already exists with the name of the virtual image, or if you specify the name of an existing disk, the engine creates a disk with a different name.

    Similarly, beginning in version 6.2.1.1, you can specify whether to keep or delete the virtual disk when you delete the environment by setting the preserve\_os\_disk property. For example, the following code names the storage disk `TempStorageDisk` and deletes it when the environment is deleted:

    ```
    linux_image_A:
      type: OS::Nova::Server
      properties:
        name: "My image A"
        image: "MyImage123"
      metadata:
        azure_properties:
          resource_group: { get_param: resource_group }
          storage_account: { get_param: storage_account }
          preserve_os_disk: false
          os_disk_name: "TempStorageDisk"
    ```

    To delete disks from your storage account manually, open the Azure web portal, open your storage account, click **Blobs**, click **vhds**, click a virtual disk, and then click **Delete**.

    The palette shows resources from the currently connected account, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).

3.   Add other Azure resources, such as networks, from the palette to the blueprint. Blueprints can contain only custom images, networks, and storage accounts from the same resource group. You can determine which resource group contains these resources through the Azure web portal or command-line client.
4.   Specify how to install the HCL® UrbanCode™ Deploy agent. In version 6.2.1, the engine always uses the `cloud-init` package. Therefore, in version 6.2.1, only images that have the `cloud-init` package preinstalled are supported. In version 6.2.1.1 and later, you can use the use\_cloudinit property to specify how to install the agent:
    -   In version 6.2.1.1 and later, by default, Azure Marketplace images use the Azure Linux Agent or related tools on Windows images to install the HCL UrbanCode Deploy agent. In this case, after you provision the environment, you can see the script that the server used to set up the image and install the HCL UrbanCode Deploy agent. In the Azure web portal, select the storage account, open the `Blobs` list, open the `scripts` container, and browse to the script, such as `myImage.sh`. This script is encoded in base 64 to hide passwords and reduce the file size.
    -   In version 6.2.1.1 and later, by default, custom images use the `cloud-init` package to install the HCL UrbanCode Deploy agent.
    -   To specify whether to use the Azure tools or the `cloud-init` package, set the use\_cloudinit property. For example, to use the `cloud-init` package, set the use\_cloudinit property to true, as shown in the following code:

        ```
        linux_image_A:
          type: OS::Nova::Server
          properties:
            name: "My image A"
            image: "MyImage123"
          metadata:
            azure_properties:
              resource_group: { get_param: resource_group }
              storage_account: { get_param: storage_account }
              use_cloudinit: true
        ```

5.   Apply a security group to each image. The security group determines which ports are open on the images, so you must use a security group that has the appropriate ports open for agent communication. See [Firewall and communication configuration](../../com.ibm.udeploy.install.doc/topics/agent_firewalls.md). 
6.   If the image requires a floating IP address, at the bottom right of the image, click ![](../images/icons/ip_not_set.gif) the IP address icon. 
7.   Set the default resource group and storage account in the blueprint parameters, as in the following example code: 

    ```
    resource_group:
      type: string
      description: 'The Azure resource group'
      default: 'MyStorageGroup'
    storage_account:
      type: string
      description: 'The Azure storage account'
      'MyStorageAccount'
    ```

8.   Create a configuration file and externalize properties to the file. See [Editing configuration files](blueprint_configs.md).
9.   In the configuration file, ensure that the core OpenStack types are mapped to Azure types. The configuration file must have mapping similar to the following code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::Azure::Server
      OS::Neutron::Port : IBM::Azure::NetworkInterface
      OS::Neutron::FloatingIP : IBM::Azure::PublicIP
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

