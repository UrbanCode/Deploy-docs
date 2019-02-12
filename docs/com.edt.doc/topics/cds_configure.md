# Setting up images, regions, and flavors for the cloud discovery service and engine

The cloud discovery service provides information about available images, regions, and flavors to the blueprint design server. This service runs with a default set of options, but you can customize these options so your images, regions and flavors are shown in the blueprint designer.

While you can use the default settings for the cloud discovery service, you can also configure it with information about the specific regions, flavors, and images, as applicable, that you use with your clouds. If you configure the cloud discovery service, you must provide the same information about regions and flavors to your engine.

**Parent topic:** [Blueprint design server configuration](../../com.edt.doc/topics/c_node_administering_bds.md)

## Setting up images, regions, and flavors on the cloud discovery service

If you customize the cloud discovery service to provide an accurate list of regions and flavors in the blueprint designer, add them to the cloud discovery service configuration file. When you customize some clouds, you must also list the specific images that you use.

1.   On the computer that hosts the cloud discovery service and the blueprint design server, create a configuration file or update the existing configuration file. To create a configuration file, copy the template in the file /usr/lib/python2.7/site-packages/clouddiscoveryservice/default\_settings.py. The blueprint design server displays images, regions, and flavors based on the contents of this configuration file. You must provide the images, regions, and flavors for your clouds in the configuration file.

    **Note:** The flavor and region information in this configuration file must match the information in the /usr/lib/heat/ibm-cloud-ext/resources/ibm-cloud-discovery.conf file on the Heat engine. For example, if you are using vCenter, the flavors for that cloud are listed in the ibm-cloud-discovery.conf file. In this case, these flavors must match the flavors in the cloud discovery service configuration file. If the flavor and region information in the ibm-cloud-discovery.conf file does not match the information in the cloud discovery service file, then the images that the Heat engine provisions might not match the images that are displayed in the blueprint designer.

    The configuration file has separate sections for each cloud type. The format and content of each section differs, depending on the cloud type:

    -   For EC2, you must register regions and images in the cloud discovery service file. You must also register the instance types that you provision with the cloud discovery service. See [Registering Amazon EC2 images with the cloud discovery service](integrate_ec2_image.md).
    -   For Azure, you must register images in the cloud discovery service file. See [Registering Azure marketplace images with the cloud discovery service](integrate_azure_image.md) and [Registering Azure custom images with the cloud discovery service](integrate_azure_private.md).
    -   For vRealize Automation, you must register flavors in the cloud discovery service file. See [Configuring VMware vRealize Automation image flavors](cloud_connect_vra_flavors.md#).
    -   For vCenter, you must register flavors in the cloud discovery service file. See [Configuring VMware vCenter image flavors](cloud_connect_vmware_flavors.md).
    -   For SoftLayer, you must register flavors in the cloud discovery service file. See [Configuring SoftLayer image flavors](cloud_connect_softlayer_flavors.md).
    -   For Google Cloud Platform, you must register image in the cloud discovery service file. See [Registering Google Cloud Platform public images](cloud_connect_google_cloud_cds.md).
    -   Also, at the bottom of the file, a section lists the default regions for the system. These regions are used only when you are connected to a cloud that does not have regions defined.

        ```
        regions: [
            {
                "id": "RegionOne",
                "name": "RegionOne"
            }]
        ```

2.   Set the system variable CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE to the location of the cloud discovery service configuration file. The file can be in any location on the system that hosts the cloud discovery service.
3.   If the cloud discovery service and blueprint design server are installed on Red Hat Enterprise Linux™ version 7, provide the location of the cloud discovery service configuration file to the `systemd` service. To do this, add the location of the file to the `systemd` service configuration file. In the Service section of the /usr/lib/systemd/system/ibm-cloud-discovery.service file, add an Environment parameter. This parameter must set the CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE system variable to the location of the cloud discovery service configuration file. For example, if the cloud discovery service configuration file is named /home/ec2-user/cloud\_discovery\_customizations.conf, the `systemd` service configuration file resembles the following code:

    ```
    [Unit]
    Description=IBM Cloud Discovery Service
    After=syslog.target network.target
    
    [Service]
    **Environment="CLOUDDISCOVERYSERVICE\_SETTINGS\_FILE=/home/ec2-user/cloud\_discovery\_customizations.conf"**
    Type=simple
    Restart=on-failure
    RestartSec=0
    ExecStart=/usr/bin/python -m clouddiscoveryservice.runserver
    
    [Install]
    WantedBy=network-online.target 
    ```

4.   Restart the cloud discovery service. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md) and [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md).
5.   If you have other cloud discovery services, copy the file to them and configure the system variables in the same way. Then, restart each other cloud discovery service. 

## Setting up regions and flavors on the engine

Now that you set up the regions and flavors on the cloud discovery service, you must also configure them on the engine.The heat engine does not need a list of available image names to provision instances of those images.

1.   On the computer that hosts the Heat engine, make a backup copy of the ibm-cloud-discovery.conf file. This file is in the /usr/lib/heat/ibm-cloud-ext/resources folder.
2.   In the ibm-cloud-discovery.conf file, add regions and flavors. This file provides information for the Heat engine about regions and flavors on the target clouds.

    **Note:** The information in this file does not support wildcards such as asterisks \(\*\).

    Different clouds require different information:

    -   For Amazon EC2, Azure, and Google Cloud Platform, no information is needed in this file. You do not configure image names or families on the engine.
    -   For OpenStack and OpenStack-based clouds, no information is needed in this file.
    -   For VMware vRealize Automation Enterprise, list the flavors to use. See [Configuring VMware vRealize Automation image flavors](cloud_connect_vra_flavors.md#).
    -   For vCenter, list the flavors to use. See [Configuring VMware vCenter image flavors](cloud_connect_vmware_flavors.md).
    -   For SoftLayer, list the flavors to use. See [Configuring SoftLayer image flavors](cloud_connect_softlayer_flavors.md).
    -   Also, at the bottom of the file, a section lists the default regions for the system. These regions are used only when you are connected to a cloud that does not have regions defined.

        ```
        regions: [
            {
                "id": "RegionOne",
                "name": "RegionOne"
            }]
        ```

3.   Restart the engine. 
4.   If you are using more than one engine, copy the ibm-cloud-discovery.conf to the other engines and restart them. 

