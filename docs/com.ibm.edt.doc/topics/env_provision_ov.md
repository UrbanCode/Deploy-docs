# Provisioning cloud environments

You can provision an environment from the server or from the blueprint designer. Several different scenarios for provisioning cloud environments are available.

When you provision a cloud environment, you set aside resources on the specified cloud that you specified through a blueprint. HCL® UrbanCode™ Deploy supports two main methods of provisioning resources on clouds. The method that you choose depends on whether you automate activity on the cloud with virtual system patterns or with OpenStack Heat.

-   **Clouds that use virtual system patterns**

    To provision environments on clouds that use virtual system patterns, you create blueprints on the HCL® UrbanCode™ Deploy server. For the types of clouds on which the server can provision environments through this method, see [Connecting to clouds through HCL UrbanCode Deploy](../../com.ibm.udeploy.doc/topics/cloud_integrate_vsp_ov.md).

    To create blueprints on clouds that use virtual system patterns, see [Modeling environments for clouds that use virtual system patterns](blueprint_edit_clouds_vsp.md).

    To provision environments based on these blueprints, you create environments on the HCL® UrbanCode™ Deploy server using the blueprint as a model. See [Provisioning environments through the server \(through virtual system patterns\)](../../com.ibm.udeploy.doc/topics/env_provision_vsp.md).

-   **Clouds that you connect to via OpenStack Heat**

    To provision environments on clouds via OpenStack Heat, you create blueprints with the blueprint designer. For the types of clouds that the server can provision environments on using OpenStack Heat, see [System requirements and performance considerations](../../com.ibm.udeploy.install.doc/topics/sysRequire.md). For individual instructions for connecting to each type of supported cloud with this method, see [Connecting to clouds through the blueprint designer](security_cloud_connection.md).

    There are several different ways that you can use these blueprints to provision environments on clouds via OpenStack Heat. To provision an environment directly from the blueprint designer, see [Provisioning environments from the blueprint designer \(through OpenStack Heat\)](env_provision_edt.md). To provision an environment from the HCL® UrbanCode™ Deploy server, either as part of creating a new application environment or as part of running an application process, see [Provisioning environments from the HCL UrbanCode Deploy server \(through OpenStack Heat\)](env_provision_ucd.md).

    **Restriction:** If your heat engine is at the Juno level, you cannot provision from a composite blueprint. See [Creating composite blueprints](blueprint_import.md#).


-   **[Provisioning environments from the blueprint designer \(through OpenStack Heat\)](../../com.ibm.edt.doc/topics/env_provision_edt.md)**  
If you connect to the target cloud through OpenStack Heat, you can provision an environment directly from the blueprint designer.
-   **[Provisioning environments from the HCL UrbanCode Deploy server \(through OpenStack Heat\)](../../com.ibm.edt.doc/topics/env_provision_ucd.md)**  
You can create application environments in the HCL UrbanCode Deploy server by using blueprints from the blueprint designer.
-   **[Provisioning environments through the server \(through virtual system patterns\)](../../com.ibm.udeploy.doc/topics/env_provision_vsp.md)**  
You can provision environments on a cloud system as part of creating an application environment on the HCL UrbanCode Deploy server.
-   **[Applying changes to a provisioned environment](../../com.ibm.edt.doc/topics/blueprint_apply.md)**  
After you provision a blueprint, you can modify the HCL UrbanCode Deploy components and cloud images in the environment that you provisioned.
-   **[Updating environments](../../com.ibm.edt.doc/topics/env_update.md)**  
You can apply a blueprint to a running environment to update the environment.
-   **[Deleting cloud environments](../../com.ibm.edt.doc/topics/env_delete.md)**  
You can delete provisioned cloud environments from the HCL UrbanCode Deploy server or from the blueprint designer.

