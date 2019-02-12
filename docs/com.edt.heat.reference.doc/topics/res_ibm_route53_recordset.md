# AWS::Route53::RecordSet

This resource type represents a DNS record set, which translates host names to IP addresses.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|comment|String|False|Core|A description for the record set.|
|hosted\_zone|String|True|Core|The ID of the hosted zone.|
|identifier|String|False|Core|An identifier that differentiates among multiple resource record sets that have the same combination of DNS name and type.|
|name|String|True|Core|Name of the domain. This must be a fully specified domain, ending with a period as the last label indication.|
|region|String|False|Core|The region for this record set, for latency-based routing.|
|resource\_records|List|True|Core|List of resource records to add.|
|ttl|Integer|False|Core|The resource record cache time to live \(TTL\), in seconds.|
|type|String|True|Core|The type of records in the set, such as CNAME or A.|
|weight|Integer|False|Core|The relative portion of traffic for the resource record set that is routed to the associated location.|

**Parent topic:** [Amazon Route 53 resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_route53.md)

