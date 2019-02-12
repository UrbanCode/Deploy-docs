# AWS::Route53::HostedZone

This resource type represents a hosted zone, which contains DNS records for domains.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|comment|String|False|Core|A description for the hosted zone.|
|name|String|True|Core|Name of the domain. This must be a fully specified domain, ending with a period as the last label indication.|
|private\_zone|Boolean|False|Core|Specify True for a private hosted zone. The default is False for a public zone.|
|vpc\_id|String|False|Core|For private zones, specify the ID of the associated VPC.|
|vpc\_region|String|False|Core|For private zones, specify the associated regions for the VPC.|

**Parent topic:** [Amazon Route 53 resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_route53.md)

