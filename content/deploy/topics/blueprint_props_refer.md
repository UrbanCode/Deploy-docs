# Referring to blueprint properties, attributes, and parameters {#blueprint_props_refer .task}

Blueprints contain parameters, and resources within blueprints contain attributes and properties. In many cases, you must refer to one of these values from another location in the blueprint.

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

You specify the type of each parameter to limit the values of the parameter. The available parameter types are string, number, comma\_delimited\_list, JSON, and Boolean. Parameters with the comma\_delimited\_list type contain a list of values that use the following format: `[“one”, “two”]`. If a parameter is assigned the Boolean type, you must select the appropriate value from a list.

In some cases, you must enclose the argument of the get\_param function in single quotation marks. For example, to obtain the user ID of the individual that provisioned an environment from a parameter, use the following get\_param statement:

```
{ get_param : 'IBM::UCD::USER' }
```

Blueprint resources also have attributes and properties. Attributes are values that describe the physical environment resources and are often available only after stack provisioning. Properties are input values that are specified at or before provisioning time, such as the size of a storage volume. The previous example showed how to use parameters to specify values for properties.

For another example, assume that you are provisioning a two-node environment: one node hosts a database, and the other node hosts a web application. The web application needs the location of the database, but this information is not available until the environment is provisioned. Therefore, you must refer to the attribute that represents the IP address of the database node.

To refer to an attribute, use the get\_attr function. For example, assume that the database node is set up as in the following blueprint code:

```
db-server:
  type: OS::Nova::Server
  properties:
    networks:
        - port: { get_resource: db-server_external-net_port }
    flavor: { get_param: flavor }
    image: "19033a29-9662-4b9d-b164-67884876fc91"
    key_name: { get_param: key_name }
    name: "db-server"
```

This node, which is of the resource type `OS::Nova::Server`, has an attribute that is named `networks`. This attribute is not shown in the code; it is implied by the resource type. \(The code shows a property that is named `networks`, which is not to be confused with the attribute with the same name.\) The attributes for a resource and, if applicable, the deployment output of any Chef components that are used in the blueprint determine the available output values. For information about the properties and attributes on Heat resources, see the reference for the resource type. See [Heat resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ov.md).

To view the value of the `networks` attribute for the database node, specify it in the output section of the blueprint code, as shown in the following code:

```
outputs:
  networks:
    description: networks
    value: {get_attr: [db-server_external-net, networks]}
```

After you provision an environment, its output properties are visible on the **Environments** page.

You can also combine attributes in output properties. For example, to view the URL of the environment that you provision, you might include the following get\_attr function:

```
outputs:
 webserver_url:
  description: JKE Webserver URL
  value:
   str_replace:
    template: http://host:9080
    params:
     host:  {get_attr: [webserver__to__genericnet__floating_ip,  floating_ip_address]} 
```

The web application can refer to the attribute to retrieve the database IP address. As an example, the web component might have the following blueprint code:

```
web-component:
  type: IBM::UrbanCode::SoftwareDeploy::UCD
  properties:
    apply_config: { get_resource: web-component_sw_config }
    server: web-server
    version: 5.1
    agent_timeout: "360"
    inputs:
      db-server-ip: { get_attr: [db-server, networks, external-net, 0] }
```

This code shows a custom property that is named `db-server-ip`, which represents the IP address of the database node. To get the IP address, the code uses the get\_attr function. The arguments of the function refer first to the resource `db-server`, then to the attribute `networks`. The attribute `networks` is a map \(a Python `dict` type\) that lists the network resources to which the database node is attached and the IP addresses in those networks. For example, an OpenStack system might have two networks: an internal network with IP addresses for use within the network and an external network with externally accessible floating IP addresses. This map might look like the following example:

```
{
  "internal-net":[192.168.80.11, 192.168.80.12],
  "external-net":[172.24.50.21, 172.24.50.22]
}
```

This map lists the IP addresses that are assigned to the resource. The IP addresses are organized according to the network to which the IP address belongs. This example lists two internal network IP addresses and two external network IP addresses. The last two arguments in the get\_attr function in the example refer to the name of the network and the index of the IP address, based on this map.

In this way, the following example of the get\_attr function refers to the resource `db-server`, the attribute `networks`, the network `external-net`, and the first IP address in the network that is assigned to the resource.

```
{ get_attr: [db-server, networks, external-net, 0] }
```

Externalize the properties and parameters in configuration files. See [Externalizing properties in blueprints](../../com.ibm.edt.doc/topics/blueprint_props_externalize.md).

**Parent topic:** [Blueprint properties, attributes, and parameters](../../com.ibm.udeploy.doc/topics/blueprint_props_ov.md)

