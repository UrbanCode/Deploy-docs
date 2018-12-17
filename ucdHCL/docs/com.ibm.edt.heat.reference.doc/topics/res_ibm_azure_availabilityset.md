# IBM::Azure::AvailabilitySet

This type represents a Microsoft™ Azure availability set. It can create a new availability set.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|managed|Boolean|False|Core|If the availability set supports virtual machines with managed disks, then the value is `True`.|
|name|String|True|Core|The name of the availability set. If the specified name exists, a new, unique name is created.|
|platform\_fault\_domain\_count|Integer|False|Core|The number of fault domains that are used. The default is `2`.|
|platform\_update\_domain\_count|Integer|False|Core|The number of update domains that are used. The default is `5`.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Core|The name of the resource group.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|availability\_set\_id|String|The Azure ID of the availability set.|
|name|String|The name of the availability set.|
|show|String|The details of the availability set.|
|sku|String|The SKU of the availability set.|
|virtual\_machines|String|The list of virtual machines in the availability set.|

## Example

This example creates a new availability set:

```
 azure_av_set:
    type: IBM::Azure::AvailabilitySet
    properties:
     resource_group: test-rg
     name: avtest_1
     platform_update_domain_count: 6
     platform_fault_domain_count: 3
     managed: True 
    metadata:
     azure_properties:
      tags: 
       servertag: testvalue
       
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

