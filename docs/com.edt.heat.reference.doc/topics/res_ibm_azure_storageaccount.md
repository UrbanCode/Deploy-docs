# IBM::Azure::StorageAccount

This type represents a Microsoft™ Azure storage account.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|access\_tier|String|False|Core|Required for BlobStorage accounts. Valid values are: -   `Hot` \(the default\)
-   `Cool`

|
|account\_name|String|True|Core|The name of the storage account. This name must be unique in the Azure namespace. If the specified name is not available, a new unique name is created.|
|account\_type|String|True|Core|The type of storage account to create. Valid values are: -   `Standard_LRS`
-   `Standard_ZRS`
-   `Standard_GRS`
-   `Standard_RAGRS`
-   `Premium_LRS`

|
|account\_kind|String|False|Core|The kind of account. Valid values are:-   `Storage` \(the default\)
-   `BlogStorage`

|
|enable\_blob\_encryption|Boolean|False|Core|Specify true to enable blob encryption. The default is false.|
|resource\_group\_name|String|True|Core|The resource group name.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|access\_keys|String|The access keys on the storage account.|
|name|String|The name of the storage account.|
|primary\_endpoints|String|The primary endpoints \(queue, table, blob, or file\) of the storage account.|
|secondary\_endpoints|String|The secondary endpoints \(queue, table, blob, or file\) of the storage account.|
|storage\_account\_id|String|The ID of the storage account.|
|show|String|The details of the storage account.|
|tier|String|The tier of the storage account: `Standard` or `Premium`.|

## Example

This example creates a `Premium_LRS` storage account with the specified tags.

```
 azure_stgacct_1:
    type: IBM::Azure::StorageAccount
    properties:
      account_name: teststg1
      account_type: Premium_LRS
      account_kind: Storage
      resource_group_name: test-rg
    metadata:
      azure_properties:
        tags:
          tag1 : test-1
          tag2 : test-2
```

**Parent topic:** [Microsoft Azure resource types](../../com.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

