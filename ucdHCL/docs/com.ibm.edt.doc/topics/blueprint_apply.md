# Applying changes to a provisioned environment

After you provision a blueprint, you can modify the HCL® UrbanCode™ Deploy components and cloud images in the environment that you provisioned.

-   Create a blueprint and configuration file, and ensure that these files are appropriate for the target cloud system. Depending on your cloud system, see
    -   [Modeling environments for SoftLayer](blueprint_edit_softlayer.md#)
    -   [Modeling environments for Amazon Web Services](blueprint_edit_ec2.md)
    -   [Modeling environments for VMware vCenter](blueprint_edit_vc.md)
    -   [Modeling environments for VMware vRealize Automation](blueprint_edit_vra.md)
    -   [Modeling environments for OpenStack and OpenStack-based clouds](blueprint_edit_os.md)
    -   [Modeling environments for Microsoft Azure](blueprint_edit_azure.md).
    -   [Modeling environments for Google Cloud Platform](blueprint_edit_google_cloud.md)

-   Provision the blueprint to the target cloud system. See [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md#).

1.   Open the blueprint that you used to provision an environment, and change its contents. 

    You can make any of the following changes to the blueprint.

    -   Add more components to images that contain components.
    -   Modify component versions.
    -   Add more images to a network.
    -   Delete images from a network.
    -   Delete components from an image.
    If you extended a Kilo, Liberty, or Mitaka level heat engine and provision to clouds that support autoscaling groups, you also can make any of the following changes:

    -   Add components or images that contain components to an autoscaling group.
    -   Create an autoscaling group that contains an image.
    -   Modify the version of components in an autoscaling group.
    -   Delete components from an image in an autoscaling group.
    In addition, if you provision the blueprint to only OpenStack clouds, you can change the instance name.

    However, you cannot make the following changes to the blueprint:

    -   Add a component to an image that does not contain a component.
    -   Select a different process to deploy a component.
    -   Change the name of an image.
    -   Remove all components from an image.
    -   In all clouds except for OpenStack, modify the image, including modifying the volume size and type. If you modify the image, your instance is removed and replaced with a new instance that meets your new specifications. This new instance has a different IP address than the previous instance.
2.   Click **Apply**. The Apply Blueprint to an Existing Environment window is displayed.
3.   From the **Environment** list, select the environment to apply the changes to. 
4.   From the **Configuration** list, select the configuration file to use while you update the environment. 
5.   Click **Apply**. The contents of the environment are updated to match the revised blueprint.

To review the status of the changes to the environment, click **Environments** and expand the environment. In the **Stack Status** column, note the status for each image.

**Parent topic:** [Provisioning cloud environments](../../com.ibm.edt.doc/topics/env_provision_ov.md)

