# IBM::UrbanCode::SoftwareConfig::UCD

This resource type represents configuration properties that are used when you deploy a component, including the name of the component process that deploys the component.In most cases, this resource type is associated with a [IBM::UrbanCode::SoftwareDeploy::UCD](res_ibm_urbancode_softwaredeploy_ucd.md) resource.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|application|String|True|Core|The name of the application in HCL® UrbanCode™ Deploy|
|component\_process|String|True|Core|The component process that deploys the component|
|component\_process\_timeout|String|False|Core|The component process execution timeout value|
|environment\_name|String|False|Core|The name of the environment to be created in HCL UrbanCode Deploy|
|inputs|Map|False|Core|The environment properties on an HCL UrbanCode Deploy component|
|name|String|False|Core|The name of the component to deploy|
|tag|String|False|Core|The component tag of the components to deploy|
|ucd\_password|String|True|Core|The password for the user name|
|ucd\_server\_url|String|True|Core|The URL of the HCL UrbanCode Deploy server|
|ucd\_username|String|True|Core|The user name with which to connect to HCL UrbanCode Deploy|

This resource type has no attributes.

**Parent topic:** [HCL UrbanCode Deploy resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md)

