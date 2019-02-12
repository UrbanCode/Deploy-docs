# IBM::Google::PublicIPAssociation

This resource type represents the public IP association on Google Cloud Platform.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|fixed\_ip\_address|String|False|Core|IP address to use if the port has multiple addresses|
|floatingip\_id|String|True|Core|ID of the floating IP to associate.|
|port\_id|String|True|Core|ID of an existing port with at least one IP address to associate with this floating IP.|

This resource type has no attributes.

**Parent topic:** [Google Cloud Platform resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)

