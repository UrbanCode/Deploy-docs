# IBM::VRA::SoftwareComponent

This resource represents a discovered component. It points to its software component type that is already defined in VMware vRealize Automation. You can set variables to the script type by using the input properties that follow. This new type for vRealize Automation is not overridden in the configuration file.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|inputs|Map|False|Core|The input properties on a vRealize Automation component|
|name|String|True|Core|The name of the software component in the vRealize Automation blueprint|
|server|String|True|Core|The resource reference to the server that hosts this component|
|type|String|True|Core|The type of the existing vRealize Automation component.|

**Parent topic:** [VMware vRealize Automation resource types](../../com.edt.heat.reference.doc/topics/VRA_heat_types_ov.md)

