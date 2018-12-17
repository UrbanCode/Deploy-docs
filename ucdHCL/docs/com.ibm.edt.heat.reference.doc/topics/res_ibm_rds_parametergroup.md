# IBM::RDS::ParameterGroup

This resource type represents a parameter group on RDS.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|description|String|True|Core|A description of the parameter group.|
|family|String|True|Core|The family for the database parameter group, such as `oracle-ee-11.2` . This family must be compatible with the database type.|
|name|String|True|Core|The name for the parameter group.|
|parameters|List|False|Core|The parameter values to update, in a key-value format.|
|type|String|False|Core|The type of the parameter group, in a string or cluster format.|

This resource type has no attributes.

**Parent topic:** [Amazon RDS resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_rds.md)

