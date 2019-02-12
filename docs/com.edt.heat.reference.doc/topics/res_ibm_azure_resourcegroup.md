# IBM::Azure::ResourceGroup

This type represents a Microsoft™ Azure resource group.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|resource\_group\_name|String|True|Core|The name of the resource group. If the specified name exists, a new unique name is created.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the resource group.|
|resource\_group\_id|String|The ID of the resource group.|
|show|String|The details of the resource group.|

## Example

This example creates a resource group with the specified tags.

```
  azure_resource_group:
    type: IBM::Azure::ResourceGroup
    properties:
      resource_group_name: test-rg
    metadata:
      azure_properties:
        tags:
          tag1 : test-1
          tag2 : test-2
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

