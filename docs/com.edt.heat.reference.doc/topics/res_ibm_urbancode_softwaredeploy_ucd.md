# IBM::UrbanCode::SoftwareDeploy::UCD

This resource type represents a deployment instance of a component.In most cases, this resource type is associated with a [IBM::UrbanCode::SoftwareConfig::UCD](res_ibm_urbancode_softwareconfig_ucd.md) resource.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|agent\_naming\_scheme|String|False|Core|The naming scheme used for an agent, when set to `server-name`, then the server name of the operating system node will be appended to the agent name|
|agent\_timeout|String|False|Core|The amount of time in seconds that the resource waits for the agent to come online|
|alt\_process|String|False|Core|Name of the new process to be run by the component|
|apply\_config|String|False|Core|A resource reference that captures configuration information|
|inputs|Map|False|Core|The resource properties on an HCL® UrbanCode™ Deploy component|
|server|String|False|Core|A resource reference to the server that hosts this deployment|
|subgroup|String|False|Core|Name of the subgroup to check for under the agent|
|version|String|False|Core|The name or identifier of the component version to deploy, or "LATEST" for the most recent version|
|ucd\_client\_timeout|String|False|Core|The amount of time in seconds for REST API calls to the HCL UrbanCode Deploy server to complete|

|Name|Description|
|----|-----------|
|application\_name|The name of the application to modify on the server.|
|component\_name|The name of the component to deploy or update.|
|component\_path|The fully qualified hierarchical path of the component in the resource tree.|
|component\_process|The name or ID of the component process to run for the component.|
|component\_tag|The name or ID of the component tag to be deployed or updated.|
|status|The status of the deployment.|
|ucd\_password|The password or token of the user to authenticate as with the server.|
|ucd\_server\_url|The web URL of the IBM UrbanCode Deploy server. For example, https://mydevops-server.com:8443|
|ucd\_username|The user name to authenticate as with the server.|
|url|The URL of the deployed component|

**Parent topic:** [HCL UrbanCode Deploy resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_ucd_ov.md)

