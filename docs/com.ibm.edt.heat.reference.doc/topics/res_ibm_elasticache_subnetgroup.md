# IBM::ElastiCache::SubnetGroup

This resource type represents an Amazon ElastiCache subnet group, which is a collection of subnets for cache clusters.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|description|String|True|Core|The description of the cache subnet group.|
|name|String|True|Core|The name of the cache subnet group.|
|subnet\_ids|List|True|Core|A list of VPC subnet IDs.|

|Name|Description|
|----|-----------|
|vpc\_id|The VPC ID of the cache subnet group.|

**Parent topic:** [Amazon ElastiCache resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_elasticache_ov.md)

