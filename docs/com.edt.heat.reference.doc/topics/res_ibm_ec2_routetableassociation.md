# IBM::EC2::RouteTableAssociation

This resource type represents a route table association on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::RouterInterface.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|port\_id|String|False|Core|The ID of the port. You must specify either a port ID or a subnet ID.|
|router\_id|String|True|Core|The ID of the router.|
|subnet\_id|String|False|Core|The ID of the subnet. You must specify either a port ID or a subnet ID.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

