# IBM::EC2::VPC

This resource type represents a virtual private cloud \(VPC\) on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::Net.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|Administrative status of the network.|
|cidr|String|True|Extended|The CIDR block will apply to the VPC.|
|dhcp\_agents\_ids|List|False|Core|IDs of the DHCP agent to schedule the network. The default policy setting in Neutron restricts use of this property to administrative users.|
|enable\_dns\_hostnames|Boolean|False|Extended|Set to true if DNS hostnames are provided for the instances that are launched in this VPC.|
|enable\_dns\_support|Boolean|False|Extended|Set to true if a DNS server is provided by Amazon for the VPC.|
|instance\_tenancy|String|False|Extended|Allows tenancy of instances launched in the VPC.|
|name|String|False|Core|Symbolic name for the network. The name is not required to be unique.|
|shared|Boolean|False|Core|If true, the network is shared across all tenants. The default policy restricts use of this attribute to administrative users only.|
|tenant\_id|String|False|Core|ID of the tenant that owns the network. Only administrative users can set the tenant ID. You cannot use an authorization policy to set the tenant ID.|
|value\_specs|Map|False|Core|Additional parameters to include in the "network" object in the creation request. Typically, additional parameters are specific to installed hardware or extensions.|

This resource type has no attributes.

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

