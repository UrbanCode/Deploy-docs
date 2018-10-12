# Blueprint properties, attributes, and parameters {#blueprint_props_ov .concept}

Blueprint properties, attributes, and parameters store information that is used in provisioning cloud environments.

## Properties { .section}

Most blueprint resources can have one or more properties. These properties are input values that are specified at or before provisioning time. Blueprint properties provide information about the resources. For example, the following code shows a server node. It has several properties, including the ID of the image and the name of the node.

```
web-server:
  type: OS::Nova::Server
  properties:
    flavor: "small"
    image: "14243a29-9662-4b9d-b164-67884876fc91"
    key_name: "my_key"
    name: "web-server"
    availability_zone: "my_zone"
```

For more information about using properties in blueprints, see [Externalizing properties in blueprints](../../com.ibm.edt.doc/topics/blueprint_props_externalize.md). To limit the valid values for parameters, see [Adding constraints to blueprint properties and parameters](blueprint_props_constraints.md).

## Parameters { .section}

Each blueprint begins with a list of parameters. You can specify these parameters in the blueprint, in a configuration file, or at provisioning time. For example, the following code lists the parameter `flavor`, which represents the size of a provisioned image, and the parameter `key_name`, which represents the security key for a provisioned image.

```
parameters:
  flavor:
    type: string
    description: Flavor to be used for compute instance
    default: "m1.small"
  key_name:
    type: string
    description: Name of key-pair to be used for compute instance
    default: "MyKey"
```

To refer to these parameters in other places in the blueprint, use the get\_param function. For example, the following code shows a server node. The properties for the node refer to the parameters in the previous example.

```
web-server:
  type: OS::Nova::Server
  properties:
    flavor: { get_param: flavor }
    image: "14243a29-9662-4b9d-b164-67884876fc91"
    key_name: { get_param: key_name }
    name: "web-server"
```

When you provision environments from the blueprint, the parameters appear in the provisioning window. In that window, you can accept the values in the source code or specify new values. To limit the valid values for parameters, see [Adding constraints to blueprint properties and parameters](blueprint_props_constraints.md).

## Attributes { .section}

Attributes are output values that are available after provisioning. Attributes are commonly used to provide relevant derived values, such as the IP address of a provisioned instance. For an example of using attributes, see [Referring to blueprint properties, attributes, and parameters](blueprint_props_refer.md).

For information on referring to properties, attributes, and parameters, see [Externalizing properties in blueprints](../../com.ibm.edt.doc/topics/blueprint_props_externalize.md).

-   **[Referring to blueprint properties, attributes, and parameters](../../com.ibm.udeploy.doc/topics/blueprint_props_refer.md)**  
Blueprints contain parameters, and resources within blueprints contain attributes and properties. In many cases, you must refer to one of these values from another location in the blueprint.
-   **[Passing properties from blueprints to the resource tree](../../com.ibm.udeploy.doc/topics/env_props_BDS.md)**  
From the blueprint designer, you can set component environment properties and component resource properties in blueprint source code.
-   **[Externalizing properties in blueprints](../../com.ibm.edt.doc/topics/blueprint_props_externalize.md)**  
Rather than hardcoding values in a blueprint, you can externalize properties to parameters. Then, you can specify values in a configuration file or specify values when you provision an environment.
-   **[Adding constraints to blueprint properties and parameters](../../com.ibm.udeploy.doc/topics/blueprint_props_constraints.md)**  
You can add constraints to blueprint properties and parameters to limit the values for those properties and parameters.
-   **[Modeling environments with referenced resources](../../com.ibm.edt.doc/topics/blueprint_ref_resources.md)**  
Rather than adding specific resources to a blueprint, you can add referenced resources. Referenced resources include images, networks, routers, storage volumes, security groups, and components. Referenced resources are generic when you create the blueprint. You can then specify the exact resource to use at provisioning time. By using referenced resources, you can create one blueprint that you can provision on multiple clouds. For example, you can create a blueprint that you can provision for a development environment and for a testing environment, and use different resources in the two environments.
-   **[Options for deploying agents](../../com.ibm.edt.doc/topics/blueprint_agent_options.md)**  
Typically, you do not edit the options that are used when IBM® UrbanCode® Deploy agents are installed on virtual images. However, you can edit the code that is embedded in an agent resource to change how the agent is installed.

**Parent topic:** [Modeling environments for clouds through OpenStack Heat](../../com.ibm.edt.doc/topics/blueprint_edit_clouds.md)

