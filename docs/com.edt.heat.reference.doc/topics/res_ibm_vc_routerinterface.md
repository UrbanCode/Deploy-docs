# IBM::VCenter::RouterInterface

This resource type represents a router interface on VMware vCenter. You must use VMware NSX to access this resource type.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|port\_id|String|False|Core|The port ID. You should specify either the subnet or port\_id.|
|router\_id|String|True|Core|The router ID.|
|subnet|String|False|Core|The subnet. You should specify either the subnet or port\_id|
|subnet\_id|String|False|Core|The subnet for the port on which the members of the pool are connected.|

This resource type has no attributes.

**Parent topic:** [VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

