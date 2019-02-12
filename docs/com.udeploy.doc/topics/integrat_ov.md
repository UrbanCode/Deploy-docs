# Overview of integrations

HCL® UrbanCode™ Deploy supports integrations with other IBM® products, products from others, and certain cloud systems.

HCL UrbanCode Deploy integrates with IBM UrbanCode Release so that you can manage the release of complex interdependent applications. See [Integrating with HCL UrbanCode Deploy](http://www-01.ibm.com/support/knowledgecenter/SS4GCC_6.1.1/com.ibm.urelease.doc/topics/installIntegrate_udeploy.html).

Most integrations with HCL UrbanCode Deploy are accomplished by using plug-ins. Plug-ins provide tools for creating component processes and integrations.

See the following page on IBM developerWorks® for information about plug-ins that support other products: [UrbanCode Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

-   **[Connecting to clouds through the blueprint designer](../../com.edt.doc/topics/security_cloud_connection.md)**  
To create a connection to a cloud to use with the blueprint designer, you use OpenStack Heat. You specify the location of the identity server and the engine to use. The steps are different for each type of cloud.
-   **[Configuring images for use with the blueprint designer](../../com.edt.doc/topics/cloud_connect_vm_requirements.md)**  
You must configure images to work with the blueprint designer.
-   **[Connecting engines to Keystone servers](../../com.udeploy.install.doc/topics/install_engine_new_keystone.md)**  
If you have an engine that is configured to work with the blueprint design server, you can connect it to a Keystone server for a new cloud.
-   **[Integrating with Chef](../../com.edt.doc/topics/integrate_chef.md)**  
Chef can automate infrastructure tasks, such as installing databases and application servers. By integrating the blueprint designer with Chef, you can apply Chef roles to images in blueprints. When you provision environments, the environments run the Chef automation scripts that are based on those roles.
-   **[Connecting to clouds through HCL UrbanCode Deploy](../topics/cloud_integrate_vsp_ov.md)**  
The HCL UrbanCode Deploy server can use virtual system patterns from cloud systems such as IBM Cloud Orchestrator to create dynamic environments.
-   **[Configuring virtual system pattern-based clouds](../../com.udeploy.install.doc/topics/cloud_configure.md)**  
To create dynamic environments on a cloud system that uses virtual system patterns, you must install a script package on your cloud system.
-   **[Integrating with IBM Rational Asset Manager](../topics/ramintegrat_cpt.md)**  
You can use IBM Rational® Asset Manager to store and catalog build outputs, test results, and related packages as part of component processes in HCL UrbanCode Deploy.
-   **[Integrating with IBM Rational Test Workbench](../topics/rtwintegrat_cpt.md)**  
You can use IBM Rational® Test Workbench to virtualize services and to run integration tests as part of component processes in HCL UrbanCode Deploy.
-   **[Integrating with cloud and mobile services with IBM Bluemix DevOps Connect](../topics/installIntegrate_UCR_cloud_cp.md)**  
IBM Bluemix DevOps Connect coordinates communication between IBM UrbanCode Release, HCL UrbanCode Deploy, and the IBM Cloud and Bluemix services.
-   **[Provisioning environments through the server \(through virtual system patterns\)](../topics/env_provision_vsp.md)**  
You can provision environments on a cloud system as part of creating an application environment on the HCL UrbanCode Deploy server.
-   **[z/OS considerations for UrbanCode Deploy](../topics/zos_ch.md)**  
UrbanCode Deploy includes support for the z/OS platform. Although the articles in this Knowledge Center for using UrbanCode Deploy to deploy applications, certain platform-specific configuration factors must be considered when using a z/OS model.

