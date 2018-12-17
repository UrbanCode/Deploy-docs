# IBM::EC2::AutoScalingGroup

This resource type represents an automatic scaling group on Amazon Elastic Compute Cloud. It extends the type OS::Heat::AutoScalingGroup.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availability\_zones|List|True|Extended|List of availability zones.|
|cooldown|Integer|False|Core|Cooldown period, in seconds.|
|desired\_capacity|Integer|False|Core|Requested initial number of resources.|
|health\_check\_grace\_period|Integer|False|Extended|Length of time, in seconds, to wait after an instance starts before the health of the instance is checked.|
|health\_check\_type|String|False|Extended|The service to use to check health. The following values are allowed:-   ELB
-   EC2

|
|launch\_config|String|False|Extended|Name of the launch configuration. You must specify either the resource parameter or the launch\_config parameter.|
|load\_balancers|List|False|Extended|List of load balancers.|
|max\_size|Integer|True|Core|Maximum number of resources in the group. The value of the max\_size parameter cannot be less than zero.|
|min\_size|Integer|True|Core|Minimum number of resources in the group. The value of the min\_size parameter cannot be less than zero.|
|name|String|False|Core|Name of automatic scaling group.|
|placement\_group|String|False|Extended|The physical location of the cluster placement group that was created in Amazon Elastic Compute Cloud.|
|resource|Map|False|Core|Resource definition for the resources in the group, in HOT format. The value of this property is the definition of a resource just as if it was declared in the template itself. You must specify either the resource parameter or the launch\_config parameter.|
| | | | | |
|vpc\_zone\_identifier|String|False|Extended|A comma-separated string of subnet identifiers of virtual private clouds.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

