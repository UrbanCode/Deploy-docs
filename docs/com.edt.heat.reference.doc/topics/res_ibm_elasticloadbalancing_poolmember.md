# IBM::ElasticLoadBalancing::PoolMember

This resource type represents the members of a load balancing pool.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|address|String|True|Core|The IP address of the pool member on the pool network.|
|admin\_state\_up|Boolean|False|Core|The administrative state of the pool member. The default value is `true`.|
|pool\_id|String|True|Core|The ID of the load balancing pool.|
|protocol\_port|Integer|True|Core|The TCP port on which the pool member listens for requests or connections. The protocol\_port value must be between 0 to 655535.|
|weight|Integer|False|Core|The weight of the pool member in the pool. The weight value must be between 0 and 256, and the default value is 1.|

This resource type has no attributes.

**Parent topic:** [Amazon ElasticLoadBalancing resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_elasticloadbalancing_ov.md)

