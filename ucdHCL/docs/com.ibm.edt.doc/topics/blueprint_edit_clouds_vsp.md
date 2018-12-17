# Modeling environments for clouds that use virtual system patterns

To model environments for clouds that use virtual system patterns \(VSPs\), on the server, import a virtual system pattern as a resource template and then create a blueprint that is based on the resource template.

-   Connect to a cloud that uses VSPs. See [Connecting to clouds through HCL UrbanCode Deploy](../../com.ibm.udeploy.doc/topics/cloud_integrate_vsp_ov.md). The following clouds that use VSPs are supported by the HCL UrbanCode Deploy server:
    -   IBM Cloud Orchestrator version 2.4 or later
    -   IBM SmartCloud® Orchestrator versions 2.2 and 2.3
    -   IBM PureApplication® System version 1.0 or later
    -   IBM Workload Deployer version 3.1.0.6 or later
-   Create an application.

    **Restriction:** The names of HCL UrbanCode Deploy elements, such as environments, applications, and resource templates, that you use with a VSP cannot contain asterisk \(\*\), backslash \(\\\), or forward slash \(/\) characters.


This method applies only to clouds that use VSPs. To model environments on clouds through OpenStack Heat, see [Modeling environments for clouds through OpenStack Heat](blueprint_edit_clouds.md).

1.   Create VSPs on the target cloud. See [Creating virtual system patterns for resource templates](../../com.ibm.udeploy.doc/topics/resources_template_pattern.md).
2.   Import the VSPs as resource templates. See [Importing resource templates from clouds](../../com.ibm.udeploy.doc/topics/resources_template_import_cloud.md).
3.   Create blueprints for the environments. See [Creating blueprints for cloud environments that use virtual system patterns](../../com.ibm.udeploy.doc/topics/blueprint_create_vsp.md).

Now you can provision environments from the blueprints. See [Provisioning environments through the server \(through virtual system patterns\)](../../com.ibm.udeploy.doc/topics/env_provision_vsp.md).

-   **[Creating virtual system patterns for resource templates](../../com.ibm.udeploy.doc/topics/resources_template_pattern.md)**  
To provision dynamic environments from a cloud system, you must create a virtual system pattern that specifies the contents of the environment.
-   **[Importing resource templates from clouds](../../com.ibm.udeploy.doc/topics/resources_template_import_cloud.md)**  
If you have a virtual system pattern on a cloud system, you can import that pattern as a resource template. This resource template is a pattern from which you can provision cloud resources.
-   **[Creating blueprints for cloud environments that use virtual system patterns](../../com.ibm.udeploy.doc/topics/blueprint_create_vsp.md)**  
Blueprints for clouds that use virtual system patterns \(VSPs\) map the components of an application to the agents on the virtual images in the VSP.

**Parent topic:** [Modeling cloud environments with the blueprint designer](../../com.ibm.edt.doc/topics/blueprint_ov.md)

