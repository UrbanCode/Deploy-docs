# IBM::EC2::LaunchConfiguration

This resource type represents a launch configuration on Amazon Elastic Compute Cloud.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|image\_id|String|True|Core|Amazon Machine Image \(AMI\) ID.|
|instance\_type|String|True|Core|Instance type \(flavor\).|
|key\_name|String|False|Core|SSH key to use with instances.|
|name|String|False|Core|Name of launch configuration.|
|security\_groups|String|False|Core|Security groups to add to instances.|
|user\_data|String|False|Core|User data to apply to instances.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

