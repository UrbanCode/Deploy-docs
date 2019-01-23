# IBM::UrbanCode::ResourceTree

This resource type represents a change or addition to the HCL® UrbanCode™ Deploy resource tree.

The resource tree organizes the resources in HCL UrbanCode Deploy, such as agents and deployed components. For more information, see [Resources](../../com.ibm.udeploy.doc/topics/resources_ch.md).

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|application|String|True|Core|The name of the application in HCL UrbanCode Deploy|
|application\_process\_request\_id|String|False|Core|The application process request id for the current deployment|
|base\_resource\_group|String|False|Core|The base resource group name which will contain the created child resources|
|inputs|String|False|Core|The environment properties on an HCL UrbanCode Deploy application|
|password|String|True|Core|The password for the user name|
|team\_mappings|List|False|Core|A list of one or more teams to assign new resources to|
|ucd\_client\_timeout|String|False|Core|The amount of time in seconds for REST API calls to the HCL UrbanCode Deploy server to complete|
|urbancode\_deploy\_url|String|True|Core|The URL of the HCL UrbanCode Deploy server|
|username|String|True|Core|The user name with which to connect to HCL UrbanCode Deploy|

|Name|Description|
|----|-----------|
|application\_name|The application that is associated with the component|
|application\_process\_request\_id|The application process request id for the current deployment|
|environment\_name|The environment that is associated with the component|
|url|The URL of the deployed component|

**Parent topic:** [HCL UrbanCode Deploy resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md)

