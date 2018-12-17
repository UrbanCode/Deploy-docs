# Modeling environments for VMware vRealize Automation

To model a VMware vRealize Automation Enterprise \(vRA\) environment, log in with a vRealize Automation cloud project and specify the vRealize Automation-specific information in a blueprint.

-   Connect the blueprint design server to a cloud system. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   Make sure that your user account is authenticated to a cloud system. See [Setting up access to clouds in the blueprint designer](../../com.ibm.udeploy.admin.doc/topics/security_auth_bds.md).
-   Connect the blueprint design server to the server. See [Connecting the blueprint design server to the server](../../com.ibm.udeploy.doc/topics/ucdp_integrate.md).
-   Log in to the blueprint designer.
-   At the top of the page, select the cloud project and region to use.

After you integrate the blueprint designer with vRA, you can access many vRA artifacts from the blueprint designer. These artifacts include images in the vCenter cloud that is integrated with vRA, vRA catalog items that represent vRA blueprints, and networks. Your vRA permissions determine the kinds of blueprints that you can create and provision from the blueprint designer.

|Blueprint type|Blueprint description|Applicable vRA roles|
|--------------|---------------------|--------------------|
|The blueprint contains a customized existing vRA catalog item.|These blueprints contain only a vRA catalog item and the HCL® UrbanCode™ Deploy software components that you add to it. When you provision this blueprint, no additional assets are created on your vRA server. To provision this environment, the catalog item must contain a vRA software resource that represents an HCL UrbanCode Deploy agent. See [Creating agent components in VMware vRealize Automation](VRA_agent_component.md#).| -   Support User
-   Business User
-   Infrastructure Architect
-   Software Architect

 |
|The blueprint contains an assembly of vRA artifacts.|These blueprints do not involve a vRA catalog item. They can comprise any other vRA artifacts and HCL UrbanCode Deploy components. When you provision this environment, vRA assets, including blueprints and software components for the HCL UrbanCode Deploy agents that install HCL UrbanCode Deploy components on images, are created.| -   Infrastructure Architect
-   Software Architect

 |
|The blueprint contains artifacts that were imported from an existing vRA catalog item.|When you import a vRA catalog item into a blueprint, you add all the artifacts that the catalog item contains to the blueprint. You can add more vRA assets and HCL UrbanCode Deploy components to the blueprint. When you provision this environment, vRA assets, including blueprints and software components for the HCL UrbanCode Deploy agents that install HCL UrbanCode Deploy components on images, are created. The original vRA catalog item is unchanged.| -   Infrastructure Architect
-   Software Architect

 |

When you provision some blueprints, the blueprint designer creates artifacts on your vRA server. These artifacts represent the HCL UrbanCode Deploy blueprint that you provisioned and HCL UrbanCode Deploy agents that are installed on the new images. You cannot provision this blueprint from vRA, and you must not delete the blueprints or software components from vRA.

1.   Create the blueprint. See [Creating files with the blueprint designer](blueprint_edit.md#).
2.   Add resources from vRealize Automation catalog items to the blueprint. 
    1.   From the **VRA Catalog** drawer, drag a catalog item to the blueprint. 
    2.   In the VRA Catalog Options window, select the catalog item type. The vRA roles available to your cloud project determine which option you select. See [Table 1](#blueprint_types).

        In version 6.2.3.1 and later, select from these options:

        -   **Import artifacts from this catalog item**: Import all of the artifacts that are contained in the vRA catalog item to the blueprint.
        -   **Customize this catalog item**: Customize an existing vRA catalog item within the blueprint.
        In version 6.2.3, select from these options:

        -   **Import Catalog Item**: Import all of the artifacts that are contained in the vRA catalog item to the blueprint.
        -   **Request Existing Catalog Item**: Customize an existing vRA catalog item within the blueprint.
    3.   Click **OK**. 
3.   Add resources from the palette to the blueprint. The roles that your vRealize Automation account is assigned determine which resources you can include in the blueprints that you provision. See [Table 1](#blueprint_types).

    The palette shows resources from the currently connected cloud, which is shown in the upper-right corner of the page. For more information on working with the blueprint designer, see [Editing blueprint diagrams](blueprint_diagram.md) and [Editing blueprint source code](blueprint_source.md).

4.   Specify the vRealize Automation service and entitlement. If you did not configure a new service and a new entitlement for use with the blueprint designer, you must specify the service and entitlement to use. Add the service\_name and entitlement\_name properties to the IBM::VRA::Deployment resource and define their values, as shown in the following code:

    ```
    vra_deployment:
      type: IBM::VRA::Deployment
        properties:
          deploy_timeout: 8000
          destroy_timeout:8000
          **entitlement\_name: My\_Entitlement\_Name**
          **service\_name: My\_Service\_Name**
             servers:
             - { get_resource: sever1 }
             - { get_resource: server2 }
    ```

    **Note:** If you configured a default service and entitlement for the blueprint designer, you do not need to specify them in this resource. See [Configuring services and entitlements in VMware vRealize Automation](VRA_service_entitle.md#).

5.   Create a configuration file and externalize properties to the file. See [Editing configuration files](blueprint_configs.md).
6.   In the configuration file, ensure that the core OpenStack types are mapped to VMware vRealize Automation types. The configuration file must have mapping similar to the following code:

    ```
    resource_registry:
      OS::Nova::Server : IBM::VRA::Server
      OS::Neutron::Port : IBM::VRA::NetworkInterface
      OS::Neutron::FloatingIP : IBM::VRA::FloatingIP
      OS::Neutron::FloatingIPAssociation : IBM::VRA::FloatingIPAssociation
      OS::Neutron::SecurityGroup : IBM::VRA::SecurityGroup
    ```


Add the components of your application to the blueprint. See [Deploying components with blueprints](blueprint_deploy_env.md).

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

