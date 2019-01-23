# Configuring virtual system pattern-based clouds

To create dynamic environments on a cloud system that uses virtual system patterns, you must install a script package on your cloud system.

You must have a user account on a cloud system. This account must have permission to create script packages, to read information about virtual system patterns, IP groups, cloud groups, and environment profiles, and to create and delete virtual environments. See the documentation for your cloud system for more information about setting up permissions. For example, for IBM® PureApplication® System, see [https://www.ibm.com/support/knowledgecenter/SSCRSX\_2.1.0/doc/iwd/aac\_user\_permissions.dita](https://www.ibm.com/support/knowledgecenter/SSCRSX_2.1.0/doc/iwd/aac_user_permissions.dita).

For this type of cloud integration, the following cloud systems are supported:

-   IBM Cloud Orchestrator version 2.4 or later
-   IBM SmartCloud® Orchestrator versions 2.2 and 2.3
-   IBM PureApplication System version 1.0 or later
-   IBM Workload Deployer version 3.1.0.6 or later

Within these cloud systems, you can provision the virtual resources in environment profiles or in cloud groups. You can also assign the virtual resources to IP groups, but only when you assign the resources to an environment profile first. For more information, see [Creating environments](../../com.ibm.udeploy.doc/topics/app_environment_create.md). You can also use virtual images with no more than one virtual network card. HCL® UrbanCode™ Deploy does not support selecting different flavors of virtual resources or virtual nodes that have a multiplicity greater than 1.

To connect to OpenStack and OpenStack-based clouds, SoftLayer®, Amazon Elastic Compute Cloud, VMware vCenter, or Microsoft™ Azure, see [Connecting to clouds through the blueprint designer](../../com.ibm.udeploy.doc/topics/../../com.ibm.edt.doc/topics/security_cloud_connection.md).

The Install HCL UrbanCode Deploy Agent package automatically installs agents on cloud resources. When you provision an environment from the cloud system, this script package installs an agent on each node in the cloud resource request. Then, these agents contact the HCL UrbanCode Deploy server, and the server adds them to the environment.

1.  Download and extract the file for agents on dynamic cloud environments.This file, which is named ibm-ucd-agent-script-package.zip, is available at the following location: [https://developer.ibm.com/urbancode/plugin/urbancode-deploy-agent-package-dynamic-cloud-environments/](https://developer.ibm.com/urbancode/plugin/urbancode-deploy-agent-package-dynamic-cloud-environments/)
2.  In your cloud system, create a script package and upload the file ibm-ucd-agent-script-package.zip to the script package.The process differs slightly for different cloud systems. For example, for most cloud systems, follow these steps:

    1.  Click **Catalog** \> **Script Packages**.
    2.  Click **New** ![](../../com.ibm.udeploy.doc/images/new_script_package.gif).
    3.  In the **Script name** field, specify the following name:

        ```
        Install IBM UrbanCode Deploy Agent
        ```

        The new script package opens.

    4.  In the **Script package file** field, upload the file ibm-ucd-agent-script-package.zip. 
    You do not need to specify default values for the parameters in this script package. The server specifies these parameters when you create an environment.


Next, model cloud environments for this cloud. See [Modeling environments for clouds that use virtual system patterns](../../com.ibm.edt.doc/topics/blueprint_edit_clouds_vsp.md).

**Parent topic:** [Overview of integrations](../../com.ibm.udeploy.doc/topics/integrat_ov.md)

