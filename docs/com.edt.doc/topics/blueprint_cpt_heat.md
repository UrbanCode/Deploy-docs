# Blueprints for clouds that you connect to through OpenStack Heat

You can provision environments on clouds through HEAT-based blueprints that you model on the blueprint design server. Heat-based blueprints use OpenStack Heat Orchestration Templates to model the infrastructure of a cloud environment, including its virtual images, network, and storage. A heat-based blueprint can also include software components to be deployed in the environment.

When you have modeled the cloud environment and software components in the blueprint, you can create or update a cloud environment based on that blueprint. The blueprint design server runs this provisioning or updating by using a Heat engine. If the blueprint includes software components, the provisioning or updating process also deploys those components through the automation processes that are specified in the blueprint. For example, blueprints can use component processes on the HCL® UrbanCode™ Deploy server. Blueprints can also specify other automation details, such as the deployment order for components.

You edit this type of blueprint in the blueprint designer. See [Modeling environments for clouds through OpenStack Heat](blueprint_edit_clouds.md).

The resources in a blueprint are instances of resource types. For more information about specific types, see [Heat resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ov.md).

A simple blueprint has the following sections:

-   **Description**

    The description is a text field that describes the blueprint.

-   **Parameters**

    The parameters section is a list of values that you can refer to from resources. You can specify default values for these parameters in the blueprint, in a configuration file, or at provisioning time.

-   **Outputs**

    Blueprints can have a list of output parameters.

-   **Resources**

    The resources in a blueprint represent the resources in the provisioned environment, including virtual images, disks, and software components.

    The following resources are commonly found in this type of blueprint:

    -   **Virtual machines \(compute nodes\)**

        Virtual machine resources \(of the type `OS::Nova::Server`\) include information about the virtual image for the machine and the networks to which the virtual machine is connected.

        **Restriction:** To be used with the blueprint designer, the virtual images must meet the requirements in [Configuring images for use with the blueprint designer](cloud_connect_vm_requirements.md).

    -   **Software components and software configurations**

        Software components \(of the type [IBM::UrbanCode::SoftwareDeploy::UCD](../../com.edt.heat.reference.doc/topics/res_ibm_urbancode_softwaredeploy_ucd.md) for HCL® UrbanCode™ Deploy components and of the type `OS::Heat::SoftwareConfig` for other pieces of software\) represent deployment instances of software. In most cases, components also have a resource of the type [IBM::UrbanCode::SoftwareConfig::UCD](../../com.edt.heat.reference.doc/topics/res_ibm_urbancode_softwareconfig_ucd.md), which represents configuration properties for the component, such as its application and any properties that it has.

        Blueprints also often have a resource that represents the HCL® UrbanCode™ Deploy agent. By default, this resource is named `ucd_agent_install_win` or `ucd_agent_install_linux`, based on the operating system of the virtual machine that is used in the blueprint. It contains the code to install an agent on the virtual machines. For more information on this resource, see [Options for deploying agents](blueprint_agent_options.md#).

    -   **Storage volumes and volume attachments**

        Storage volumes \(of the type `OS::Cinder::Volume`\) represent new virtual disks that are created when the blueprint is provisioned. Storage volume attachments \(of the type `OS::Cinder::VolumeAttachment`\) represent the connection of a virtual machine to a new or existing storage volume.

    -   **Resource trees**

        The resource tree resource \(of the type [IBM::UrbanCode::ResourceTree](../../com.edt.heat.reference.doc/topics/res_ibm_urbancode_resourcetree.md)\) represents changes or additions to the resource tree on the HCL® UrbanCode™ Deploy server. Other resources, such as virtual images, refer to the properties of the resource tree, such as the location of the server. The resource tree resource also specifies the name of the application that the blueprint relates to.

    -   **Network ports**

        When you add a network to a blueprint, the editor adds a resource of the type `OS::Neutron::Port`, which represents a port on the specified network.


**Parent topic:** [Overview of blueprints](../../com.edt.doc/topics/blueprint_cpt.md)

