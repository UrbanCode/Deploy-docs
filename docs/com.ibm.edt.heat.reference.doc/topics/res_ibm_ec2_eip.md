# IBM::EC2::EIP

This resource type represents an elastic IP \(EIP\) address on Amazon Elastic Compute Cloud. It extends the type OS::Neutron::FloatingIP.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|instance\_id|String|True|Core|ID of the instance to associate with the floating IP.|

|Name|Description|
|----|-----------|
|allocation\_id|The allocation ID of this EIP.|
|association\_id|The association ID of this EIP if it is attached to an instance.|
|domain|The domain of this EIP.|
|fixed\_ip\_address|The IP address of the associated port, if specified.|
|floating\_ip\_address|The allocated address of this IP.|
|floating\_network\_id|The ID of the network in which this IP is allocated.|
|instance\_id|The ID of an associated instance of this EIP.|
|network\_interface\_id|The ID of the network interface of this EIP if it is attached to an instance.|
|network\_interface\_owner\_id|The ID of the network interface owner if it is attached to an instance.|
|port\_id|The ID of the port that is associated with this IP|
|private\_ip\_address|The private IP address of the instance that is attached to this EIP.|
|public\_ip|The public IP address of this EIP.|
|region|The region of this EIP|
|router\_id|The ID of the router that is used as a gateway. It is set when associated with a port.|
|show|Displays all attributes.|
|tenant\_id|The tenant that owns this floating IP.|

**Parent topic:** [Amazon Elastic Compute Cloud resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ec2_ov.md)

