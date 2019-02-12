# IBM::EC2::EIPAssociation

This resource type represents an elastic IP address \(EIP\) association on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::FloatingIPAssociation.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|fixed\_ip\_address|String|False|Core|IP address to use if the port has access to multiple addresses.|
|floatingip\_id|String|True|Core|ID of the floating IP with which to associate.|
|instance\_id|String|True|Extended|ID of the instance to associate with the floating IP.|
|port\_id|String|False|Core|ID of a port with at least one IP address to associate with the floating IP. The port must exist.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

