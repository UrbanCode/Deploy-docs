# IBM::RDS::AuroraInstance

This resource type represents an Aurora instance on Amazon RDS.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone|String|True|Core|The Amazon RDS Availability Zone in which the DB instance is created.|
|cluster\_id|String|True|Core|The ID of the Aurora cluster.|
|db\_instance\_class|String|True|Core|The compute and memory capacity of the database instance, such as `d.t1.micro` or `db.m2.xlarge`.|
|engine\_version|String|True|Core|The version of the database engine to be used for this instance.|
|instance\_creation\_timeout|Integer|False|Core|The number of seconds to wait for the instance to be created. The default value is 600 seconds.|
|name|String|True|Core|The name of the Aurora instance.|
|publicly\_accessible|String|True|Core|A list of VPC subnet IDs.|

|Name|Type|Description|
|----|----|-----------|
|endpoint\_address|String|The endpoint address of the Aurora cluster.|
|endpoint\_port|String|The endpoint port of the Aurora cluster.|

## Example

This example shows how to add Aurora instances to an existing cluster.

**Note**: The following instances have different subnets; however, both instances point to the same cluster.

```
 rds-aurora-instance_1:  
    type: IBM::RDS::AuroraInstance
    properties:
      name: rds-db-instance
      cluster_id: { get_resource: rds-aurora-cluster ]
      publicly_accessible: True
      availability_zone: us-east-2b
      db_instance_class: db.t2.small
      engine_version: 5.6.10a
      instance_creation_timeout: 1800

   rds-db-instance:  
    type: IBM::RDS::AuroraInstance
    properties:
      name: rds-db-instance1
      cluster_id: { get_resource: rds-aurora-cluster ]
      publicly_accessible: True
      availability_zone: us-east-2a
      db_instance_class: db.t2.small
      engine_version: 5.6.10a
      instance_creation_timeout: 1800

    
```

**Parent topic:** [Amazon RDS resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_rds.md)

