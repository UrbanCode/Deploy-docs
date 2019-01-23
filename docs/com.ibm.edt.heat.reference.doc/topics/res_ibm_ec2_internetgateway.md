# IBM::EC2::InternetGateway

This resource type represents an Internet gateway on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::RouterGateway.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|create\_route|Boolean|False|Extended|Create default route on route table using gateway.|
|network\_id|String|False|Core|ID of the external network for the gateway.|
|router\_id|String|False|Core|ID of the router.|
|vpc\_id|String|False|Extended|The AWS VPC ID.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

