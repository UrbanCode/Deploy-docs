# IBM::EC2::RouteTable

This resource type represents a route table on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::Router.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|l3\_agent\_id|String|False|Core|ID of the L3 agent. The default policy setting in Neutron restricts usage of this property to administrative users.|
|admin\_state\_up|Boolean|False|Core|The administrative state of the router.|
|external\_gateway\_info|Map|False|Core|External network gateway configuration for a router. See [Table 2](#external_gateway_info).|
|name|String|False|Core|Router name.|
|value\_specs|Map|False|Core|Additional parameters to include in the creation request.|
|vpc\_id|String|True|Extended|The VPC to create a route table on.|

The external\_gateway\_info parameter requires a list of networks for the gateway. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|enable\_snat|Boolean|False|Enables source NAT on the router gateway.|
|network|String|True|ID or name of the external network for the gateway.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

