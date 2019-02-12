# IBM::VRA::Deployment

Set deployment timeout properties, service, and entitlement names. Deployment is a new type for VMware vRealize Automation; properties are not overridden in the configuration file.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|blueprint|String|False|Core|The blueprint name to provision. The default value is to provision the blueprint that is based on the stack name.|
|deploy\_timout|Integer|False|Core|The amount of time that the Heat engine is allotted to deploy a vRealize Automation request.|
|destroy\_timeout|Integer|False|Core|The amount of time that the Heat engine is allotted to destroy a vRealize Automation request.|
|entitlement\_name|String|False|Core|The entitlement name to add to the catalog entry.|
|request\_ID|String| |Extended|The ID of the vRealize Automation deployment request.|
|servers|List|False|Core|The servers to provision in this blueprint.|
|service\_name|String|False|Core|The Service name to add to the catalog entry.|

**Parent topic:** [VMware vRealize Automation resource types](../../com.edt.heat.reference.doc/topics/VRA_heat_types_ov.md)

