# Registering Azure custom images with the cloud discovery service

To use Microsoft™ Azure custom images in the blueprint designer, you must register the images with the cloud discovery service.

-   Configure the cloud discovery service. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.ibm.udeploy.doc/topics/cds_configure.md).
-   Create one or more Azure Resource Manager templates from Linux or Windows images. See [https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-linux-capture-image/](https://azure.microsoft.com/en-us/documentation/articles/virtual-machines-linux-capture-image/).
-   Ensure that the Azure account in the blueprint designer cloud connection has access to the Azure Resource Manager templates.
-   Ensure that the Azure resource group that each custom image is stored in contains appropriate networks and standard storage accounts. Blueprints must contain custom images, networks, and storage accounts from the same resource group. You can determine which resource group contains these resources through the Azure web portal or command-line client.

Custom images are Azure Resource Manager templates for virtual machines. You can preconfigure these images with software and configuration settings, and then store them as a template to reuse in the blueprint designer. Storing an image as a template removes information such as IP addresses and host names that can conflict with other images. In this way, you can create multiple images from this template without creating conflicts.

Only Azure Resource Manager templates are supported; classic deployment model templates are not supported.

1.   Obtain the following information for each custom image that you want to use in the blueprint designer: 
    -   The resource group that the custom image is stored in.
    -   The storage account that the custom image is stored in.
    -   The name of the Blob container that the custom image VHD file is stored in. To find the name of the Blob container, in the Azure web portal, open the storage container and then open the Blob service. The data in the Blob service is stored in folders that are called containers. You need only the name of the top-level Blob container that stores the VHD file, even if the files are in subfolders.
2.   Open the cloud discovery service configuration file in a text editor. 
3.   If the cloud discovery service configuration file does not have an Azure section, create the Azure section: 
    1.   To the `CLOUD_SETTINGS` section, add a section that looks like the following code: 

        ```
        "azure": {
            "private_images": [
                
            ]
        }
        
        ```

4.   To the Azure section of the cloud discovery service configuration file, add entries for the Blob containers that have templates that you want to use. Each entry follows this format:

    ```
    "resource_group":"resourceGroup",
    "storage_account":"storageAccount",
    "container_list":[containerList]
    ```

    -   For `resourceGroup`, specify the resource group.
    -   For `storageAccount`, specify the storage account.
    -   For `containerList`, specify a comma-separated list of Blob containers, in quotes.
    For example, the following code includes Blob containers that are named `container1` and `container2`:

    ```
    "azure": {
        "private_images": [
            {
                "resource_group": "myResourceGroup",
                "storage_account": "myStorageAccount",
                "container_list": ["container1","container2"]
            }
        ]
    }
    
    ```

    The complete section looks like the following example:

    ```
    "azure": {
        "private_images": [{
              "resource_group": "myResourceGroup",
              "storage_account": "myStorageAccount",
              "container_list": ["container1","container2"]
    }],
        "images": [
            {
                "publisher": "openlogic",
                "sku": ["6.5","6.6","6.7","7.0","7.1","7.2"],
                "offer": "CentOS",
                "display_name" : "CentOS"
            },
            {
                "publisher": "Canonical",
                "sku": ["12.04.5-LTS","14.04.4-LTS","15.10"],
                "offer": "UbuntuServer",
                "display_name": "Ubuntu Server"
            },
            {
                "publisher": "MicrosoftWindowsServer",
                "sku": ["2012-R2-Datacenter","2008-R2-SP1"],
                "offer": "WindowsServer",
                "display_name": "Windows Server"
            }
        ]
    }
    
    ```

5.   Save the file and restart the cloud discovery service. To restart the cloud discovery service, see [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md).

Now you can add the images to blueprints. When you add a custom image to a blueprint, the blueprint designer asks whether the image is a Windows or Linux image. Custom images appear in a separate drawer in the palette; this drawer appears only if the cloud discovery service successfully loads at least one custom image. If the drawer is not visible, ensure that the cloud discovery service configuration file has the correct format and the correct information about the images.

**Parent topic:** [Connecting to Microsoft Azure](../../com.ibm.edt.doc/topics/cloud_connect_azure.md)

