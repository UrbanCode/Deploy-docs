# IBM::Azure::RouteTable

This type represents a Microsoft™ Azure route table.

This resource type extends the OpenStack resource type `OS::Neutron::Router`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|name|String|True|Core|The name of the route table. If the specified name exists, a new unique name is created.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Extended|The name of the resource group.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the route table.|
|route\_table\_id|String|The Azure ID of the route table ID.|

## Example

This example creates a route table with the specified tags.

```
  azure_route_table_1:
    type: IBM::Azure::RouteTable
    properties:
      name: test-route-table
    metadata:
      azure_properties:
        tags:
          tag1 : value1
          tag2 : value2
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

