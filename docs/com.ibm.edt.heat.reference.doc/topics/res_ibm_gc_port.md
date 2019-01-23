# IBM::Google::Port

This resource type represents a port on Google Cloud Platform. It extends the type OS::Neutron::Port.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of the port.|
|allowed\_address\_pairs|List|False|Core|A list of more MAC/IP address pairs that are allowed to pass through the port. See [Table 2](#allowed_address_pairs).|
|binding:vnic\_type|String|False|Core|The VNIC type to be bound on the neutron port. To support SR-IOV PCI pass-through networking, you can request that the neutron port to be realized the following types:-   `Normal` \(virtual inc\)
-   `Direct` \(PCI pass-through\)
-   `macvtap` \(virtual interface with a tap-like software interface\)

**Note:** This binding works only for Neutron deployments that support the bindings extension.

|
|device\_id|String|False|Core|Device ID of the port.|
|device\_owner|String|False|Core|Name of the network that owns the port. The value is typically `network:floatingip`, `network:router_interface`, or `network:dhcp`.|
|fixed\_ips|List|False|Core|A list of the IP addresses to be requested for the port. See [Table 3](#fixed_ips).|
|mac\_address|String|False|Core|MAC address to apply to the port.|
|name|String|False|Core|A symbolic name for this port.|
|network|String|False|Core|The network that this port belongs to.|
|network\_id|String|True|Core|ID of the network that the port is a member of.|
|replacement\_policy|String|False|Core|Policy on how to respond to a stack-update for this resource. The following values are allowed:-   `REPLACE_ALWAYS`, which replaces the port regardless of any property changes.
-   `AUTO`, which updates the existing port for any changed update-allowed property.

|
|security\_groups|List|False|Core|The security group IDs to associate with the port.|
|value\_specs|Map|False|Core|More parameters to include in the "port" object in the creation request.|

The allowed\_address\_pairs parameter requires a list of addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|True|IP address to allow through the port.|
|mac\_address|String|False|MAC address to allow through the port.|

The fixed\_ips parameter requires a list of addresses for the port. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|False|IP address to request in the subnet for the port.|
|subnet|String|False|Subnet in which to allocate the IP address for the port.|
|subnet\_id|String|False|The ID of the subnet in which to allocate the IP address for the port.|

This resource type has no attributes.

**Parent topic:** [Google Cloud Platform resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)

