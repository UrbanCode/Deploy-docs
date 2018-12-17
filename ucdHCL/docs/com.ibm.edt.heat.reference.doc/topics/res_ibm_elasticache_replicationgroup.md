# IBM::ElastiCache::ReplicationGroup

This resource type represents a replication group, which is a group of cache clusters that synchronize their data. A primary cluster stores the data and one or more read replicas store copies of the data.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|description|String|False|Core|The description of the replication group.|
|name|String|True|Core|The name of the replication group.|
|primary\_cluster\_id|String|False|Core|The ID of the primary cache cluster. This cache cluster must already exist and have a status of available.|

|Name|Description|
|----|-----------|
|member\_clusters|The member clusters of the replication group.|
|number\_read\_replicas|The number of read replicas in the replication group, not counting the primary cluster.|
|primary\_cluster\_id|The ID of the primary cluster.|
|primary\_endpoint\_address|The primary endpoint address of the replication group.|
|primary\_endpoint\_port|The primary endpoint port of the replication group.|

**Parent topic:** [Amazon ElastiCache resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_elasticache_ov.md)

