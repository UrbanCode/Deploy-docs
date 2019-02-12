# IBM::ElastiCache::ParameterGroup

This resource type represents a parameter group, which is a group of parameters that you can apply to a cache cluster.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|description|String|True|Core|The description of the parameter group.|
|family|String|True|Core|The family for the parameter group. This family must correspond to the engine type and version, such as `redis2.6` or `memcached1.4`.|
|name|String|True|Core|The name of the parameter group.|
|parameters|List|False|Core|The parameter values to update, in a key-value format.|

This resource type has no attributes.

**Parent topic:** [Amazon ElastiCache resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_elasticache_ov.md)

