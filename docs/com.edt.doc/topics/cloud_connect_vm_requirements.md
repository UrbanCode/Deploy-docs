# Configuring images for use with the blueprint designer

You must configure images to work with the blueprint designer.

## Requirements for all cloud systems

To use images with the blueprint designer, you must do the following with each image:

-   Ensure that Linux™ images have the tar and curl programs installed.
-   Ensure that Windows™ Server 2008 images have version 2.0 or higher of the PowerShell program installed.
-   To apply Chef roles to images, configure the images as described in [Creating Chef-compatible images](integrate_chef_images.md).

Configure the images for the target cloud:

-   To use an image on OpenStack, see [Configuring OpenStack images](cloud_connect_openstack_images.md).
-   To use an image on Amazon AWS, register it with the cloud discovery service. See [Registering Amazon EC2 images with the cloud discovery service](integrate_ec2_image.md).
-   To use an image on the SoftLayer® cloud, configure it as described in [Configuring private SoftLayer images](cloud_connect_softlayer_images.md).
-   To use an image on VMware vCenter, see [Configuring VMware vCenter images](cloud_connect_vmware_images.md).
-   To use an image on Microsoft™ Azure, register it with the cloud discovery service. See [Registering Azure marketplace images with the cloud discovery service](integrate_azure_image.md). To create and use custom images on Microsoft Azure, see [Registering Azure custom images with the cloud discovery service](integrate_azure_private.md).
-   To use a custom image on Google Cloud Platform, configure it as described in [Configuring Google Cloud Platform images](cloud_connect_google_cloud_images.md#).

**Note:** Configuration for some cloud and image type combinations must be completed in the blueprint. See [Modeling environments for clouds through OpenStack Heat](blueprint_edit_clouds.md#).

**Parent topic:** [Overview of integrations](../../com.udeploy.doc/topics/integrat_ov.md)

