# Registering Azure marketplace images with the cloud discovery service

To use Microsoft™ Azure marketplace images in the blueprint designer, you must register images with the cloud discovery service.

Before you register images, configure the cloud discovery service. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.ibm.udeploy.doc/topics/cds_configure.md).

For version 6.2.1, Linux™ images that are preloaded with the `cloud-init` package are the only images that are supported. In version 6.2.1.1 and later, you can use Windows images, and you can use Linux images with or without the `cloud-init` package.

1.   Obtain the following information for each image that you want to use in the blueprint designer: 

    -   The publisher name, usually the name of the company that provides the image. For example, Canonical is the publisher of Ubuntu images.
    -   The SKU or stock-keeping unit parameter of the image, which is typically the version number of the operating system on the image.
    -   The offer parameter of the image, which is an identifier that describes the image, such as `ubuntuserver` or `openSUSE`. This identifier is not case-sensitive.
    To obtain this information, you can find the image in the Azure web portal or use the command-line interface. For example, to list information about images that are provided by Canonical and are available in the `East US` region, run the following command:

    ```
    azure vm image list eastus canonical
    ```

    To list information about SUSE images, run the following command:

    ```
    azure vm image list eastus SUSE
    ```

    From the resulting table of information, take the publisher name, the SKU value, and the offer identifier.

2.   Open the cloud discovery service configuration file in a text editor. 
3.   If the cloud discovery service configuration file does not have an Azure section, create the Azure section: 
    1.   To the `CLOUD_SETTINGS` section, add a section that looks like the following code: 

        ```
        "azure": {
            "images": [
                
            ]
        }
        
        ```

4.   To the Azure section of the cloud discovery service configuration file, add entries for each image that you want to use. Each entry follows this format:

    ```
    "publisher":"publisher",
    "sku":[listOfSKUs],
    "offer":"offer",
    "display_name":"displayName"
    ```

    -   For `publisher`, specify the publisher.
    -   For `listOfSKUs`, specify a comma-separated list of SKU values, in quotes.
    -   For `offer`, specify the offer value.
    -   For `display\_name`, specify a display name for the image in the blueprint designer.
    For example, the following code includes Ubuntu images, an openSUSE image, and CentOS images:

    ```
    "azure": {
        "images": [
            {
                "publisher": "Canonical",
                "sku": ["12.10","14.04.3-LTS","15.10"],
                "offer": "UbuntuServer",
                "display_name": "UbuntuServer"
            },
            {
                "publisher": "SUSE",
                "sku": ["13.2"],
                "offer": "openSUSE",
                "display_name": "openSUSE"
            },
            {
                "publisher": "openlogic",
                "sku": ["6.5","6.6","7.0","7.1"],
                "offer": "CentOS",
                "display_name" : "CentOS"
            }
        ]
    }
    
    ```

5.   Save the file and restart the cloud discovery service. To restart the cloud discovery service, see [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md).

Now you can add the images to blueprints.

**Parent topic:** [Connecting to Microsoft Azure](../../com.ibm.edt.doc/topics/cloud_connect_azure.md)

