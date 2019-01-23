# IBM::RDS::AuroraCluster

This resource type represents an Aurora cluster on Amazon RDS.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zone|String|False|Core|The Amazon RDS availability zone in which the cache cluster is created.|
|db\_name|String|True|Core|The name of the database.|
|engine\_version|String|False|Core|The version of the cache engine.|
|master\_password|String|True|Core| |
|master\_username|String|True|Core| |
|name|String|False|Core|The name of the cache cluster.|
|num\_cache\_nodes|Integer|False|Core|The number of cache nodes. The default value is 1.|
|parameter\_group|String|False|Core|The name of the cache parameter group that is associated with this cache cluster.|
|port|Integer|False|Core|The port number on which cache nodes accept connections.|
|subnet\_group|String|False|Core|The cache subnet group that is associated with a cache cluster. Specify this property if you are launching into a VPC.|
|vpc\_security\_group\_ids|List|False|Core|A list of VPC security group IDs.|

## Example

This example creates an Amazon RDS Aurora cluster without any instances.

```
 resources:
   rds-aurora-cluster:  
    type: IBM::RDS::AuroraCluster
    properties:
      name: rds-aurora-cluster
      port: 3306
      db_name: ibm_ucdp
      engine_version: 5.6.10a
      master_password: ucdpadmin
      master_username: ucdpadmin
      parameter_group: { get_resource: rds-cluster-parameter_group }
      subnet_group: {get_resource: rds-subnet_group }
      availability_zones:
        - us-east-2c
        - us-east-2a
        - us-east-2b
      vpc_security_group_ids:
        - sg-e119b189 #sg-e119b189(tranb)

    rds-subnet_group:
     type: IBM::RDS::SubnetGroup
     properties:
      name: os-subnet_group
      description: For aurora cluster
      subnet_ids: [subnet-1b342251, subnet-c9b31ca0, subnet-22b44659]

    rds-cluster-parameter_group:
     type: IBM::RDS::ParameterGroup
     properties:
      name: my_rds_parameter_group
      description: My RDS Parameter Group (Cluster)
      family: aurora5.6
      type: CLUSTER

    rds-instance-parameter_group:
     type: IBM::RDS::ParameterGroup
     properties:
      name: my_rds_parameter_group
      description: My RDS Parameter Group (Instance)
      family: aurora5.6

## REFERENCE{"vpc-9f08d5f6":{"type":"OS::Neutron::Net","properties":{"network_id":"vpc-9f08d5f6",
"external":"false","subnets":[{"cidr":"172.31.32.0\/20","availability_zone":"us-east-2c","name":"subnet
-1b342251","id":"subnet-1b342251"},{"cidr":"172.31.0.0\/20","availability_zone":"us-east-2a","name":"subnet
-c9b31ca0","id":"subnet-c9b31ca0"},{"cidr":"172.31.16.0\/20","availability_zone":"us-east-2b","name":"subnet
-22b44659","id":"subnet-22b44659"}]}}}

outputs: 
 blueprint_url:
  description: Blueprint Origin URL
  value: https://127.0.0.1:8443/landscaper/view/projects?open=ucdpadmin_00000000_0000_0000_0000_0000000
00002-OrionContent/Internal-Team/rds_part1.yaml.yml

    
```

**Parent topic:** [Amazon RDS resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_rds.md)

