# IBM::EC2::Subnet

This resource type represents a subnet on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::Subnet.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|allocation\_pools|List|False|Core|The start and end addresses for the allocation pools. See [Table 2](#allocation_pools).|
|auto\_assign\_public\_ip|Boolean|False|Extended|Enable the subnet to automatically assign a public IP address.|
|availability\_zone|String|True|Extended|The availability zone of the subnet.|
|cidr|String|True|Core|CIDR subnet mask.|
|dns\_nameservers|List|False|Core|A list of DNS servers to use on the subnet.|
|enable\_dhcp|Boolean|False|Core|True if DHCP is enabled and false if DHCP is disabled.|
|gateway\_ip|String|False|Core|Gateway IP address.|
|host\_routes|List|False|Core|Additional routes to add to the subnet. See [Table 3](#host_routes).|
|ip\_version|Integer|False|Core|The IP version. Allowable values are 4 and 6. By default, the ip\_version parameter is set to 4.|
|name|String|False|Core|Name of the subnet.|
|network\_id|String|True|Core|ID of the attached network.|
|tenant\_id|String|False|Core|ID of the tenant that owns the network. Only administrative users can specify a tenant ID other than their own.|
|value\_specs|Map|False|Core|Additional parameters to include in the creation request.|

The allocation\_pools parameter requires the start and end addresses for the allocation pool. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|end|String|True|End address for an allocation pool.|
|start|String|True|Start address for an allocation pool.|

The host\_routes parameter requires a list of routes. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|destination|String|True|CIDR subnet mask.|
|nexthop|String|True|IP address of the next hop to the route to add.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

