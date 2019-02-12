# IBM::SoftLayer::FloatingIP

This resource type represents a floating IP address on SoftLayer.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|fixed\_ip\_address|String|False|Core|IP address to use if the port has multiple addresses.|
|floating\_network|String|False|Core|Network to allocate floating IP from.|
|floating\_network\_id|String|False|Core| |
|port\_id|String|False|Core|ID of an existing port with at least one IP address to associate with this floating IP.|
|value\_specs|map|False|Core|Extra parameters to include in the `floatingip` object in the creation request. Parameters are often specific to installed hardware or extensions.|

|Name|Description|
|----|-----------|
|fixed\_ip\_address|The IP address of the associated port, if specified.|
|floating\_ip\_address|The allocated address of this IP.|
|floating\_network\_id|The ID of the network in which this IP is allocated.|
|port\_id|The ID of the port that is associated with this IP|
|router\_id|ID of the router used as gateway, set when associated with a port.|
|show|Displays all attributes.|
|tenant\_id|The tenant that owns this floating IP.|

**Parent topic:** [SoftLayer resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_sl_ov.md)

