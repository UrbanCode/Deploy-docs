# IBM::Azure:ServerExtension

This type represents a Microsoft™ Azure server extension. It can create a new server extension.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|auto\_upgrade\_minor\_version|Boolean|True|Core|Gets or sets whether the extension handler should be automatically upgraded across minor versions.|
|extension\_type|String|True|Core|Gets or sets the type of the extension handler.|
|name|String|True|Core|The name of the extension.|
|protected\_settings|Map|False|Core|Sets the protected settings for the extension.|
|provision\_state|String|False|Core|Gets or sets the provisioning state, which only displays in the response.|
|publisher|String|True|Core|Gets or sets the name of the extension handler publisher.|
|resource\_group\_name|String|True|Core|The name of the resource group.|
|settings|Map|False|Core|Sets the settings for the extension.|
|type\_handler\_version|String|True|Core|The version of the extension.|
|vm\_name|String|True|Core|The VM on which the extension executes.|

|Attribute|Type|Description|
|---------|----|-----------|
|show|String|The details of the extension.|

## Example

This example creates a new server extension:

```
 extension_name:
    type: IBM::Azure::ServerExtension
    properties:
     name: CustomScriptForLinux
     resource_group_name: resource group name
     vm_name:{ get_resource: CentOS }
     auto_upgrade_minor_version: true
     publisher: Microsoft.OSTCExtensions
     type_handler_version: "1.5"
     extension_type: CustomScriptForLinux
     protected_settings:
      storageAccountName: xxxxxxx 
      storageAccountKey: +xxxxxxxxx
     settings:
      fileUris: ['https://storage_url/myscript.sh']
      commandToExecute: bash myscript.sh
       
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

