# IBM::EC2::AutoScalingPolicy

This resource type represents an automatic scaling policy on Amazon Elastic Compute Cloud. It extends the type OS::Heat::ScalingPolicy.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|adjustment\_type|String|True|Core|Type of adjustment \(absolute or percentage\). The following values are allowed:-   change\_in\_capacity
-   exact\_capacity
-   percent\_change\_in\_capacity
-   ChangeInCapacity
-   ExactCapacity
-   PercentChangeInCapacity

|
|auto\_scaling\_group\_id|String|True|Core|Automatic scaling group ID to apply policy to.|
|cooldown|Number|False|Core|Cooldown period, in seconds.|
|name|String|False|Core|Name of scaling policy.|
|scaling\_adjustment|Number|True|Core|Size of adjustment.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

