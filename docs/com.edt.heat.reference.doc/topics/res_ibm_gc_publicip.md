# IBM::Google::PublicIP

This resource type represents a public IP address on a Google Cloud Platform image.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|fixed\_ip\_address |String|False|Core|IP address to use if the port has multiple addresses.|
|floating\_network |String|False|Core|Network to allocate floating IP from.|
|floating\_network\_id |String|False|Core|ID of the network in which this IP is allocated.|
|port\_id |String|False|Core|ID of the port that is associated with this IP.|
|value\_specs |Map|False|Core|Extra parameters to include in the floatingip object in the creation request. Parameters are often specific to installed hardware or extensions.|

|Name|Description|
|----|-----------|
|fixed\_ip\_address|IP address of the associated port, if specified.|
|floating\_ip\_address|The allocated address of this IP.|
|floating\_network\_id|ID of the network in which this IP is allocated.|
|port\_id|ID of the port that is associated with this IP.|
|router\_id|ID of the router that is used as gateway, set when associated with a port.|
|show|All attributes.|
|tenant\_id|The tenant that owns this floating IP.|

**Parent topic:** [Google Cloud Platform resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_gc_ov.md)

