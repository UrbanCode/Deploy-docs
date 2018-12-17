# Modeling environments for Google Cloud Platform

To model a Google Cloud Platform environment, log in with a Google Cloud cloud project and specify the Google Cloud-specific information in a blueprint.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.  Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud and region, which is shown in the upper-right corner of the page. You can access Compute Engine resources from only a single project that are available to your current region. See [Regions and Zones](https://cloud.google.com/compute/docs/regions-zones/regions-zones) in the Google Cloud Platform Compute Engine documentation.

    For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).

3.  Add volumes to the images.You can add or create volumes in addition to the boot volume for an image's operating system. Only volumes that are not attached to other virtual machine are visible in the palette. You can also create a new storage volume for the image.
4.   Add resources from the palette to the blueprint, such as virtual images. The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).
5.  Create a configuration file and externalize properties to the file.See [Editing configuration files](blueprint_configs.md).
6.  In the configuration file, ensure that the core OpenStack types are mapped to Google Cloud Platform types.The configuration file must have mapping similar to the following code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::Google::Server
      OS::Neutron::Port : IBM::Google::Port
      OS::Neutron::FloatingIP : IBM::Google::PublicIP
      OS::Neutron::FloatingIPAssociation : IBM::Google::PublicIPAssociation
      OS::Cinder::Volume : IBM::Google::Disk
      OS::Cinder::VolumeAttachment : IBM::Google::DiskAttachment
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

