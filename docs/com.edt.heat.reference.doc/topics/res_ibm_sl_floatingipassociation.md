# IBM::SoftLayer::FloatingIPAssociation

This resource represents the association of a floating IP address with a SoftLayer image.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|floatingip\_id|String|True|Core|ID of the floating IP to associate.|
|fixed\_ip\_address|String|False|Core|IP address to use if the port has multiple addresses.|
|port\_id|String|True|Core|ID of an existing port with at least one IP address to associate with this floating IP.|

This resource type has no attributes.

**Parent topic:** [SoftLayer resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_sl_ov.md)

