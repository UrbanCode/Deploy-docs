# Modeling environments for clouds through OpenStack Heat

To model environments for clouds that you connect to through OpenStack Heat, create blueprints on the blueprint design server.

This method does not apply to clouds that use virtual system patterns. To model environments for clouds that use virtual system patterns, see [Modeling environments for clouds that use virtual system patterns](blueprint_edit_clouds_vsp.md).

-   **[Modeling environments for OpenStack and OpenStack-based clouds](../../com.ibm.edt.doc/topics/blueprint_edit_os.md)**  
To model an OpenStack environment, log in with an OpenStack cloud project and use resources from your cloud system in a blueprint.
-   **[Modeling environments for Amazon Web Services](../../com.ibm.edt.doc/topics/blueprint_edit_ec2.md)**  
To model an Amazon Web Services \(AWS\) environment, log in with an AWS cloud project and specify the AWS-specific information in a blueprint.
-   **[Modeling environments for SoftLayer](../../com.ibm.edt.doc/topics/blueprint_edit_softlayer.md)**  
To model a SoftLayer® environment, log in with a SoftLayer® cloud project and specify the information that is specific to SoftLayer® in a blueprint.
-   **[Modeling environments for VMware vCenter](../../com.ibm.edt.doc/topics/blueprint_edit_vc.md)**  
To model a VMware vCenter environment, log in with a VCenter cloud project and specify the VCenter-specific information in a blueprint.
-   **[Modeling environments for VMware vRealize Automation](../../com.ibm.edt.doc/topics/blueprint_edit_vra.md)**  
To model a VMware vRealize Automation Enterprise \(vRA\) environment, log in with a vRealize Automation cloud project and specify the vRealize Automation-specific information in a blueprint.
-   **[Modeling environments for Microsoft Azure](../../com.ibm.edt.doc/topics/blueprint_edit_azure.md)**  
To model a Microsoft™ Azure environment, log in with an Azure cloud project and specify the Azure-specific information in a blueprint.
-   **[Modeling environments for Google Cloud Platform](../../com.ibm.edt.doc/topics/blueprint_edit_google_cloud.md)**  
To model a Google Cloud Platform environment, log in with a Google Cloud cloud project and specify the Google Cloud-specific information in a blueprint.
-   **[Deploying components with blueprints](../../com.ibm.edt.doc/topics/blueprint_deploy_env.md)**  
Add components to a blueprint so that when you provision environments from the blueprint, the engine automatically installs the components.
-   **[Deploying applications with blueprints](../../com.ibm.edt.doc/topics/blueprint_deploy_app.md)**  
Add all of the components in an application to a blueprint so that when you provision environments from the blueprint, the engine automatically installs the application.
-   **[Applying Chef roles to environments](../../com.ibm.edt.doc/topics/blueprint_chef.md)**  
Chef roles describe automation tasks to be run on a target system. You can apply roles to images in a blueprint.
-   **[Blueprint properties, attributes, and parameters](../../com.ibm.udeploy.doc/topics/blueprint_props_ov.md)**  
Blueprint properties, attributes, and parameters store information that is used in provisioning cloud environments.
-   **[Editing blueprints with the blueprint designer](../../com.ibm.edt.doc/topics/blueprint_create.md)**  
When you work with blueprints, you can use a graphical editor or a source-code editor.
-   **[Blueprint storage on the blueprint design server](../../com.ibm.edt.doc/topics/blueprint_storage.md)**  
 You store blueprints and configuration files that you create with the blueprint designer in Git repositories. By storing blueprints and configurations in the Git repository for a team, you can share the files with members of that team.
-   **[Modeling networks](../../com.ibm.edt.doc/topics/blueprint_network_ov.md)**  
You can refer to existing network stacks in blueprints created on the blueprint design server, or you can create new network elements.
-   **[Modeling software services](../../com.ibm.edt.doc/topics/blueprint_service_ov.md)**  
You can add software services to blueprints that you create on the blueprint design server so that your applications can access those services at provisioning time.
-   **[Providing cloud credentials in a blueprint](../../com.ibm.edt.doc/topics/blueprint_credentials.md)**  
By default, when you provision an environment from a blueprint, the environment is created by using the cloud account information of its cloud project. However, when you create a blueprint for most kinds of clouds, you can specify different user credentials.
-   **[Modeling autoscaling environments](../../com.ibm.edt.doc/topics/blueprint_autoscale.md)**  
Autoscaling environments automatically add or remove resources as demand changes.

**Parent topic:** [Modeling cloud environments with the blueprint designer](../../com.ibm.edt.doc/topics/blueprint_ov.md)

