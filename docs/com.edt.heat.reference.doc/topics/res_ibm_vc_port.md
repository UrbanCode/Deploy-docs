# IBM::VCenter::Port

This resource type represents a port on a VMware vCenter image. It extends the type OS::Neutron::Port.

This resource type is provided with the engine, but it is not implemented. You can use it in blueprints and in configuration files, but when you provision an environment, this resource type is ignored. However, the blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of this port.|
|allowed\_address\_pairs|List|False|Core|Additional MAC/IP address pairs allowed to pass through the port.|
|device\_id|String|False|Core|Device ID of this port.|
|device\_owner|String|False|Core|Name of the network owning the port. The value is typically `network:floatingip`, `network:router_interface` or `network:dhcp`.|
|fixed\_ips|List|False|Core|Desired IPs for this port. See [Table 2](#fixed_ips).|
|mac\_address|String|False|Core|MAC address to give to this port.|
|name|String|False|Core|A symbolic name for this port.|
|network\_id|String|False|Core|The network ID to set.|
|security\_groups|List|False|Core|The security group IDs to associate with the port.|
|value\_specs|Map|False|Core|Extra parameters to include in the port object in the creation request.|

The fixed\_ips parameter requires a list of addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|False|IP address desired in the subnet for this port.|
|subnet\_id|String|False|Subnet in which to allocate the IP address for this port.|

**Parent topic:** [VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

