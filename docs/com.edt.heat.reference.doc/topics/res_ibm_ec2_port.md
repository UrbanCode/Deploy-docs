# IBM::EC2::Port

This resource type represents a port on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::Port.

This resource type is provided with the engine, but it is not implemented. You can use it in blueprints and in configuration files, but when you provision an environment, this resource type is ignored. However, the blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of the port.|
|allowed\_address\_pairs|List|False|Core|A list of additional MAC/IP address pairs that are allowed to pass through the port. See [Table 2](#allowed_address_pairs).|
|device\_id|String|False|Core|Device ID of the port.|
|device\_owner|String|False|Core|Name of the network that owns the port. The value is typically `network:floatingip`, `network:router_interface`, or `network:dhcp`.|
|fixed\_ips|List|False|Core|A list of the IP addresses to be requested for the port. See [Table 3](#fixed_ips)|
|mac\_address|String|False|Core|MAC address to apply to the port.|
|name|String|False|Core|Symbolic port name.|
|network\_id|String|True|Core|ID of the network that the port is a member of.|
|security\_groups|List|False|Core|The security group IDs to associate with the port.|
|value\_specs|Map|False|Core|Additional parameters to include in the "port" object in the creation request.|

The allowed\_address\_pairs parameter requires a list of addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|True|IP address to allow through the port.|
|mac\_address|String|False|MAC address to allow through the port.|

The fixed\_ips parameter requires a list of addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|False|IP address to request in the subnet for the port.|
|subnet\_id|String|False|Subnet in which to allocate the IP address for the port.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

