# IBM::RDS::Instance

This resource type represents a database instance on RDS.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|allocated\_storage|String|False|Core|The name of the database option group that is associated with this instance.|
|availability\_zone|String|False|Core|The EC2 Availability Zone in which the DB instance is created.|
|backup\_retention\_period|Integer|False|Core|The number of days for which automated backups are retained.|
|backup-window|String|False|Core|The daily time range during which automated backups are created, with the format `hh24:mi-hh24:mi`, such as `23:30-23:50` .|
|db\_instance\_class|String|False|Core|The compute and memory capacity of the database instance, such as `d.t1.micro` or `db.m2.xlarge`.|
|db\_name|String|False|Core|For MySQL or PostgreSQL, the name of the database to create. For Oracle, the SID of the instance. For SQLServer, specify `null`.|
|engine|String|True|Core|The database engine.|
|engine\_version|String|True|Core|The version of the database engine to be used for this instance.|
|license\_model|String|False|Core|The license model information for this instance.|
|instance\_creation\_timeout|Integer|False|Core|The number of seconds to wait for the instance to be created.|
|maintenance\_window|String|False|Core|The daily time range for Amazon RDS to apply pending modifications, with the format `hh24:mi-hh24:mi`, such as `23:30-23:50` .|
|master\_password|String|True|Core|The password for the master database user.|
|master\_username|String|True|Core|The user name of the master user for the client database instance.|
|multi\_az|Boolean|False|Core|Specifies if the database instance is a multi-availability zone deployment.|
|name|String|True|Core|The name of the RDS database instance.|
|option\_group|String|False|Core|The name of the database option group that is associated with the instance.|
|parameter\_group|String|False|Core|The name of the database parameter group that is associated with the instance.|
|port|Integer|False|Core|The port that the database instance uses for application connections.|
|publicly\_accessible|Boolean|False|Core|Specify `yes` to allow EC2 instances and devices outside the VPC to connect to the database instance.|
|subnet\_group|String|False|Core|The database subnet group that is associated with a database instance. Specify this parameter if you are launching into a VPC.|
|vpc\_security\_group\_ids|List|False|Core|A list of VPC security group IDs.|

|Name|Description|
|----|-----------|
|endpoint\_address|The endpoint address of the database instance.|
|endpoint\_port|The endpoint port of the database instance.|

**Parent topic:** [Amazon RDS resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_rds.md)

