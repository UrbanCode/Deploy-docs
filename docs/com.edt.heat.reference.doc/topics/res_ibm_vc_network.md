# IBM::VCenter::Network

This resource type represents a network on VMware vCenter. You must use VMware NSX to access this resource type.

This resource type is provided with the engine, but it is not implemented. You can use it in blueprints and in configuration files, but when you provision an environment, this resource type is ignored. However, the blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|A Boolean value that specifies the administrative status of the network. The default value is `true`.|
|appliance\_size|String|False|Extended|The size of the edge appliance.|
|datastore|String|False|Extended|The datastore to put the VM in.|
|dhcp\_agent\_ids|List|False|Core|The IDs of the DHCP agent to schedule the network.**Note:** The default policy setting in Neutron restricts usage of this property to administrative users only.

|
|edge\_name|String|True|Extended|The name of the edge appliance.|
|name|String|False|Core|A string that specifies a symbolic name for the network, which is not required to be unique.|
|resource\_pool|String|False|Extended|The resource pool to put the VM in.|
|shared|Boolean|False|Core|Whether this network should be shared across all tenants.**Note:** The default policy setting restricts usage of this attribute to administrative users only.

|
|tenant\_id|String|False|Core|The ID of the tenant that owns the network. Only administrative users can set the tenant identifier, and the identifier cannot be changed by using authorization policies.|
|transport\_zone\_id|String|True|Extended|The transport zone ID.|
|value\_specs|Map|False|Core|Extra parameters to include in the "network" object in the creation request. Parameters are often specific to installed hardware or extensions.|

|Name|Description|
|----|-----------|
|edge\_id|The ID of the service gateway edge.|
|logical\_switch\_id|The ID of the logical switch.|
|portgroup\_id|The ID of the distributed virtual port group.|

**Parent topic:** [VMware vCenter resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_vc_ov.md)

