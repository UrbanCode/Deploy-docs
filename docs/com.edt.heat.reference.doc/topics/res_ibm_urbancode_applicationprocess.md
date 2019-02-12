# IBM::UrbanCode::ApplicationProcess

This resource type represents the properties that are used when a blueprint contains an HCL® UrbanCode™ Deploy application process that deploys components.

Application processes that deploy components contain steps that install individual components. You can use application processes that were defined in HCL UrbanCode Deploy when you provision environments to clouds by using the blueprint designer. See [Deploying applications with blueprints](../../com.edt.doc/topics/blueprint_deploy_app.md#).

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|application|String|True|Core|The name of the application in HCL UrbanCode Deploy|
|application\_process|String|False|Core|The application process request ID for the current deployment.|
|environment|String|False|Core|The environment the application process is deployed to.|
|inputs|Map|False|Core|The application process properties on an HCL UrbanCode Deploy application.|
|snapshot|String|False|Core|The application snapshot that contains the component and process versions for the deployment.|
|ucd\_client\_timeout|String|False|Core|The amount of time in seconds for REST API calls to the HCL UrbanCode Deploy server to complete.|
|ucd\_password|String|True|Core|The password for the user name.|
|ucd\_server\_url|String|True|Core|The URL of the HCL UrbanCode Deploy server.|
|ucd\_username|String|True|Core|The user name with which to connect to the HCL UrbanCode Deploy server.|

|Name|Description|
|----|-----------|
|application\_name|The application that is associated with the component.|
|application\_process\_request\_id|The application process request ID for the current deployment.|
|environment\_name|The environment that is associated with the component.|
|url|The URL of the deployed component.|

**Parent topic:** [HCL UrbanCode Deploy resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md)

