# Updating environments

You can apply a blueprint to a running environment to update the environment.

-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Create a blueprint and configuration file, and ensure that these files are appropriate for the target cloud system:
    -   [Modeling environments for SoftLayer](blueprint_edit_softlayer.md#)
    -   [Modeling environments for Amazon Web Services](blueprint_edit_ec2.md)
    -   [Modeling environments for VMware vCenter](blueprint_edit_vc.md)
    -   [Modeling environments for VMware vRealize Automation](blueprint_edit_vra.md)
    -   [Modeling environments for OpenStack and OpenStack-based clouds](blueprint_edit_os.md)
    -   [Modeling environments for Microsoft Azure](blueprint_edit_azure.md).
    -   [Modeling environments for Google Cloud Platform](blueprint_edit_google_cloud.md)
-   Add components from HCL® UrbanCode™ Deploy to the blueprint; see [Deploying components with blueprints](blueprint_deploy_env.md).
-   Create an application environment on the HCL UrbanCode Deploy server.

When you create a blueprint in the blueprint editor and add components, the blueprint appears on the HCL UrbanCode Deploy server as an application process. You can run this process on an existing environment to update the environment to match the blueprint.

For example, you can change the component versions that are deployed to the environment and then run the application process to deploy the new versions. You can also add virtual images to the environment.

When you update an environment in this way, the things that you can change depend on what parts of an environment the target cloud can update without re-provisioning the environment. Some target clouds can update different things than other clouds.

1.  Follow these steps to update an environment by applying a blueprint:
2.   In the blueprint designer, edit the blueprint to show the desired state of the environment, and then save the blueprint. 
3.   In the HCL UrbanCode Deploy server, open the application. 
4.   Next to the environment, click **Request Process** ![](../images/icons/request_process_icon.gif). 
5.   In the Run Process window, in the **Process** list, select the blueprint. If the blueprint does not appear, make sure that it is connected to the application; see [Deploying components with blueprints](blueprint_deploy_env.md).
6.   Click **Set Properties**. 
7.   On the Blueprint Properties page, specify the cloud project and region to use. 
8.   In the **Blueprint Version** field, specify the version of the blueprint to use. The default version for all blueprints is `1.0`.
9.   In the **Configuration** field, specify the configuration file to use. 
10.  If you selected a configuration file, in the **Configuration Version** field, specify the version of that file to use. 
11.  Customize the property values for the blueprint. For example, in most cases, specify the zone for the environment in the **availability\_zone** field.

    For some clouds, click **Image Parameters** and then specify the flavor for the environment images in the **Flavor** field. If the list of flavors does not contain the flavors that you expect, make sure that you registered the flavors with the cloud discovery service. See [Configuring SoftLayer image flavors](cloud_connect_softlayer_flavors.md) or [Configuring VMware vCenter image flavors](cloud_connect_vmware_flavors.md).

    In most cases, you select an SSH key by name in the **Key Name** field under **Image Parameters**. However, for VMware clouds, paste the contents of the SSH public key in this field.

12.  Click **OK**. 

The HCL UrbanCode Deploy runs the application process, which applies the blueprint to the environment.

**Parent topic:** [Provisioning cloud environments](../../com.ibm.edt.doc/topics/env_provision_ov.md)

