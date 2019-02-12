# IBM::ElastiCache::Cluster

This resource type represents a cache cluster, which is a collection of cache nodes.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone|String|False|Core|The EC2 availability zone in which the cache cluster is created.|
|cache\_node\_type|String|False|Core|The compute and memory capacity of nodes in the cache cluster.|
|cluster\_creation\_timeout|Integer|False|Core|Number of seconds to wait for cluster to be created.|
|engine|String|False|Core|The name of the cache engine, such as `redis` or `memcached`.|
|engine\_version|String|False|Core|The version of the cache engine.|
|name|String|False|Core|The name of the cache cluster.|
|num\_cache\_nodes|Integer|False|Core|The number of cache nodes. The default value is 1.|
|parameter\_group|String|False|Core|The name of the cache parameter group that is associated with this cache cluster.|
|port|Integer|False|Core|The port number on which cache nodes accept connections.|
|replication\_group\_id|String|False|Core|The replication group to which this cache cluster belongs. If this parameter is specified, the cache cluster is added to the specified replication group as a read replica. Otherwise, the cache cluster is a standalone primary that is not part of any replication group.|
|subnet\_group|String|False|Core|The cache subnet group that is associated with a cache cluster. Specify this property if you are launching into a VPC.|
|vpc\_security\_group\_ids|List|False|Core|A list of VPC security group IDs.|

|Name|Description|
|----|-----------|
|first\_node\_endpoint\_address|The endpoint address of the first node in the cluster|
|first\_node\_endpoint\_port|The port of the first address in the cluster|

**Parent topic:** [Amazon ElastiCache resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_elasticache_ov.md)

