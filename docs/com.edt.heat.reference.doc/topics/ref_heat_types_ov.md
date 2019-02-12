# Heat resource types

The engine includes custom Heat resource types that represent resources on cloud systems and artifacts from the HCL® UrbanCode™ Deploy server.

These custom Heat types are in addition to the standard Heat resource types. For more information about the Heat Orchestration Templates \(HOT\), see the following reference information.[http://docs.openstack.org/developer/heat/template\_guide/hot\_spec.html](http://docs.openstack.org/developer/heat/template_guide/hot_spec.html). The standard resource types are described on the following page: [http://docs.openstack.org/developer/heat/template\_guide/index.html](http://docs.openstack.org/developer/heat/template_guide/index.html).

To see a list of the types that are installed on your engine, open a command-line window and run the following command:

```
heat resource-type-list
```

To see information about a specific type, including its properties, use the heat resource-type-show command. For example, to see information about the `IBM::UrbanCode::SoftwareDeploy::UCD` type, run the following command:

```
heat resource-type-show IBM::UrbanCode::SoftwareDeploy::UCD
```

-   **[Resource type properties: core and extended](../../com.edt.heat.reference.doc/topics/heat_types_properties.md)**  
In blueprints, Heat resource types have two types of properties: core and extended. Core properties are inherited from a base type and extended properties are added to a type that comes with HCL UrbanCode Deploy.
-   **[Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)**  
These Heat resource types represent elements on Amazon Elastic Compute Cloud \(EC2\).
-   **[Amazon ElastiCache resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_elasticache_ov.md)**  
These Heat resource types represent elements on Amazon ElastiCache.
-   **[Amazon ElasticLoadBalancing resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_elasticloadbalancing_ov.md)**  
These Heat resource types represent elements on Amazon ElasticLoadBalancing.
-   **[Amazon RDS resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_rds.md)**  
These Heat resource types represent elements of Amazon Relational Database Service.
-   **[Amazon Route 53 resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_route53.md)**  
These Heat resource types represent elements of Amazon Route 53 domain name system \(DNS\) service.
-   **[Amazon S3 resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_s3_ov.md)**  
These Heat resource types represent elements on Amazon Simple Storage System \(S3\).
-   **[Google Cloud Platform resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)**  
This Heat resource type represents elements on Google Cloud Platform.
-   **[HCL UrbanCode Deploy resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md)**  
These Heat resource types represent elements on the server.
-   **[Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)**  
These Heat resource types represent elements on the Microsoft Azure Cloud.
-   **[SoftLayer resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_sl_ov.md)**  
This Heat resource type represents elements on SoftLayer.
-   **[VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)**  
These Heat resource types represent elements on VMware vCenter.
-   **[VMware vRealize Automation resource types](../../com.edt.heat.reference.doc/topics/VRA_heat_types_ov.md)**  
These Heat resource types represent elements on the cloud. To install these types into a Heat engine, see

**Parent topic:** [Extending product function](../../com.udeploy.doc/topics/c_node_extending.md)

