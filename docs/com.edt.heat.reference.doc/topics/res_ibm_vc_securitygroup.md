# IBM::VCenter::SecurityGroup

This resource type represents a security group on VMware vCenter. It extends the type OS::Neutron::SecurityGroup. You must use VMware NSX to access this resource type.

This resource type is provided with the engine, but it is not implemented. You can use it in blueprints and in configuration files, but when you provision an environment, this resource type is ignored. However, the blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|description|String|False|Core|Description of the security group.|
|name|String|False|Core|A string that specifies a symbolic name for the security group, which is not required to be unique.|
|rules|Map|False|Core|List of security group rules.|

The rules parameter requires a list of rules for the security group. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|direction|String|False|The direction in which the security group rule is applied. For a compute instance, an ingress security group rule matches traffic that is incoming \(ingress\) for that instance. An egress rule is applied to traffic leaving the instance. Valid values are `ingress` and `egress`.|
|ethertype|String|False|Ethertype of the traffic. Valid values are `IPv4` and `IPv6`.|
|port\_range\_max|Integer|False|The maximum port number in the range that is matched by the security group rule. The port\_range\_min attribute constrains the port\_range\_max attribute. If the protocol is ICMP, this value must be an ICMP type.|
|port\_range\_min|Integer|False|The minimum port number in the range that is matched by the security group rule. If the protocol is TCP or UDP, this value must be less than or equal to the value of the port\_range\_max attribute. If the protocol is ICMP, this value must be an ICMP type.|
|protocol|String|False|The protocol that is matched by the security group rule. Valid values include `tcp`, `udp`, and `icmp`.|
|remote\_group\_id|String|False|The remote group ID to be associated with this security group rule. If no value is specified, then this rule uses this security group for the remote\_group\_id.|
|remote\_ip\_prefix|String|False|The remote IP prefix \(CIDR\) to be associated with this security group rule.|
|remote\_mode|String|False|Whether to specify a remote group or a remote IP prefix. Valid values are remote\_ip\_prefix and remote\_group\_id.|

This resource type has no attributes.

**Parent topic:** [VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

