# IBM::Azure::Template

This type provides the ability to deploy Microsoft™ Azure Resource Manager \(ARM\) templates. ARM template outputs can be referenced by other HEAT resources in the blueprint.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|deployment\_mode|String|False|Core|The type of deployment mode: `Incremental` or `Complete`.|
|name|String|True|Core|The name of the deployment.|
|parameters|String|False|Core|Parameters to populate the ARM template with.|
|parameters\_url|String|False|Core|A URL to a parameter resource.|
|resource\_group\_name|String|True|Core|The name of the resource group.|
|template|String|False|Core|The inline JSON representation of the ARM template.|
|template\_url|String|False|Core|A URL to an ARM template.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the network security group.|
|network\_security\_group\_id|String|The ID of the network security group.|
|show|String|The details of the template.|

## Attributes

You can reference all outputs of the ARM template as attributes. For example, assume that an ARM template has an output section like the following code:

```
"outputs": {
      "storageAccountName": {
          "type": "string",
          "value": "[variables('storageAccountName')]"
      }
  }
```

In this case, you can refer to the `storageAccountName` as an attribute.

This type also has the show attribute, which provides details about the template.

## Example

This example uses a parameter URL:

```
resources:
   template_resource:
     type: IBM::Azure::Template
     properties:
         name: { get_param: "OS::stack_name" }
         template_url: "http://server.com/arm.json"
         parameters_url: "http://server.com/arm-params.json'
         deployment_mode: "complete"
    metadata:
         azure_properties:
            resource_group: { get_param: resource_group }
```

This example uses inline parameters:

```
resources:
  template_resource:
    type: IBM::Azure::Template
    properties:
      name: { get_param: "OS::stack_name" }
      template_url: http://server.com/arm.json
      parameters:    
         storageAccountType: "Premium_LRS"
         deployment_mode: "complete"
      metadata:
         azure_properties:
            resource_group: { get_param: resource_group }
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

