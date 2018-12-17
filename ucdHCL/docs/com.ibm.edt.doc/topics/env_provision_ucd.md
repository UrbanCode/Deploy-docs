# Provisioning environments from the HCL UrbanCode Deploy server \(through OpenStack Heat\)

You can create application environments in the HCL® UrbanCode™ Deploy server by using blueprints from the blueprint designer.

-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Create a blueprint and configuration file, and ensure that these files are appropriate for the target cloud system:
    -   [Modeling environments for SoftLayer](blueprint_edit_softlayer.md#)
    -   [Modeling environments for Amazon Web Services](blueprint_edit_ec2.md)
    -   [Modeling environments for VMware vCenter](blueprint_edit_vc.md)
    -   [Modeling environments for VMware vRealize Automation](blueprint_edit_vra.md)
    -   [Modeling environments for OpenStack and OpenStack-based clouds](blueprint_edit_os.md)
    -   [Modeling environments for Microsoft Azure](blueprint_edit_azure.md).
    -   [Modeling environments for Google Cloud Platform](blueprint_edit_google_cloud.md)
-   Add components from HCL UrbanCode Deploy to the blueprint; see [Deploying components with blueprints](blueprint_deploy_env.md).

When you model application environments in the blueprint designer, the blueprints you create appear in two places on the HCL UrbanCode Deploy server: as blueprints and as application processes. Therefore, there are two ways to apply a blueprint for a cloud that you connect to through OpenStack Heat to an HCL UrbanCode Deploy environment:

-   You can create an environment from the blueprint. In this case, the blueprint creates the environment and runs the application process on the new environment.
-   You can run the application process on an existing environment. In this case, the blueprint behaves like an application process.

The following steps cover creating an environment from a blueprint. To run a blueprint on an existing environment as though the blueprint was an application process, see[Updating environments](env_update.md).

1.   On the HCL UrbanCode Deploy server, click **Applications**, select an application, and then click **Create New Environment**. The Create New Environment window opens.
2.   Give the environment a name. 
3.   In the **Blueprint** field, select the blueprint. 

    **Note:** Blueprints with a cloud icon ![](../../com.ibm.udeploy.doc/images/cloud_icon.gif) are OpenStack Heat blueprints and are managed on the blueprint designer. Blueprints without a cloud icon are managed through the HCL UrbanCode Deploy server.

4.   Specify the rest of the information that is needed to create a new environment, such as the cloud project and region to use, and then click **Next**. For more information, see [Creating environments](../../com.ibm.udeploy.doc/topics/app_environment_create.md).
5.   In the **Blueprint Version** field, specify the version of the blueprint to use. The default version for all blueprints is `1.0`.
6.   In the **Configuration** field, specify the configuration file to use. 
7.   If you selected a configuration file, in the **Configuration Version** field, specify the version of that file to use. 
8.   Customize the property values for the blueprint. For example, in most cases, specify the zone for the environment in the **availability\_zone** field.

    For some clouds, click **Image Parameters** and then specify the flavor for the environment images in the **Flavor** field. If the list of flavors does not contain the flavors that you expect, make sure that you registered the flavors with the cloud discovery service. See [Configuring SoftLayer image flavors](cloud_connect_softlayer_flavors.md) or [Configuring VMware vCenter image flavors](cloud_connect_vmware_flavors.md).

    In most cases, you select an SSH key by name in the **Key Name** field under **Image Parameters**. However, for VMware clouds, paste the contents of the SSH public key in this field.

9.   Click **Create**. 

The blueprint design server provisions the cloud resources and creates an application environment in HCL UrbanCode Deploy. Then, the HCL UrbanCode Deploy server runs the component processes that are listed in the blueprint.

**Parent topic:** [Provisioning cloud environments](../../com.ibm.edt.doc/topics/env_provision_ov.md)

