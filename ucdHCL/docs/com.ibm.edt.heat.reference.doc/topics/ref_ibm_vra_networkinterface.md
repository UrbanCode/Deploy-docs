# IBM::VRA::NetworkInterface

This resource represents a network interface on a VMware vRealize Automation image. It points to its software component type that is already defined in VMware vRealize Automation. You can set variables to the script type by using the input properties that follow. This new type for vRealize Automation is not overridden in the configuration file.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of this port.|
|allowed\_address\_pairs|List|False|Core|Additional MAC/IP address pairs allowed to pass through the port. See [Table 3](#allowed_address_pairs).|
|binding:vnic\_type|String|False|Core|The vnic type to be bound on the neutron port. To support SR-IOV passthrough networking, you can request that the neutron port to be realized as normal \(virutal nic\), direct \(pci passthrough\), or macvtap \(virtual interface with a tap-like software interface\). Note that this only works for Neutron deployments that support the bindings extension.|
|device\_id|String|False|Core|Device ID of this port.|
|device\_owner|String|False|Core|Name of the network owning the port. The value is typically `network:floatingip` or `network:router_interface` or `network:dhcp`.|
|fixed\_ips|List|False|Core|This property is provided with the engine, but it is not implemented.|
|mac\_address|String|False|Core|MAC address to give to this port.|
|name|String|False|Core|A symbolic name for this port.|
|network\_id|String|False|Core|The network ID.|
|replacement\_policy|String|False|Core|Policy on how to respond to a stack-update for this resource. `REPLACE_ALWAYS` will replace the port regardless of any property changes. `AUTO` will update the existing port for any changed update-allowed property.|
|security\_groups|List|False|Core|Security group IDs to associate with this port.|
|value\_specs|Map|False|Core|Extra parameters to include in the `\"port"\` object in the creation request.|

|Name|Description|
|----|-----------|
|admin\_state\_up|The administrative state of this port.|
|allowed\_address\_pairs|Additional MAC/IP address pairs allowed to pass through a port.|
|device\_id|Unique identifier for the device.|
|device\_owner|Name of the network owning the port.|
|fixed\_ips|Fixed IP addresses.|
|mac\_address|MAC address of the port.|
|name|Friendly name of the port.|
|network\_id|Unique identifier for the network owning the port.|
|security\_groups|A list of security groups for the port.|
|show|All attributes.|
|status|The status of the port.|
|subnets|A list of all subnet attributes for the port.|
|tenant\_id|Tenant owning the port.|

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|ip\_address|String|True|IP address to allow through this port.|
|mac\_address|String|False|MAC address to allow through this port.|

**Parent topic:** [VMware vRealize Automation resource types](../../com.ibm.edt.heat.reference.doc/topics/VRA_heat_types_ov.md)

