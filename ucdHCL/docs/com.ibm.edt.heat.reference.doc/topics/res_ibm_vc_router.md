# IBM::VCenter::Router

This resource type represents a router on VMware vCenter.

This resource type is provided with the engine, but it is not implemented. You can use it in blueprints and in configuration files, but when you provision an environment, this resource type is ignored. However, the blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|l3\_agent\_id|String|False|Core|The ID of the L3 agent. **Note:** The default policy setting in Neutron restricts usage of this property to administrative users only.

|
|admin\_state\_up|Boolean|False|Core|The administrative state of the router. The default value is `true`.|
|edge\_id|String|False|Extended|The ID of the edge appliance. The value is derived from the network if it is not specified.|
|external\_cidr|String|True|Extended|The CIDR range for external router traffic.|
|external\_gateway\_info|Map|False|Core|The external network gateway configuration for a router.|
|mtu|Integer|False|Extended|The MTU value for uplink interface.|
|name|String|False|Core|The name of the router.|
|value\_specs|Map|False|Core|Extra parameters to include in the creation request.|

The external\_gateway\_info parameter requires additional information about the network. The following table shows the properties in each list item.

|Name|Type|Required|Description|
|----|----|--------|-----------|
|enable\_snat|Boolean|False|Enables Source NAT on the router gateway. **Note:** The default policy setting in Neutron restricts usage of this property to administrative users only.

|
|network|String|True|The ID or name of the external network for the gateway.|

This resource type has no attributes.

**Parent topic:** [VMware vCenter resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

