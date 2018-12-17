# IBM::Azure::NetworkSecurityGroup

This type represents a Microsoft™ Azure network security group.

This resource type extends the OpenStack resource type `OS::Neutron::SecurityGroup`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|name|String|True|Core|The name of the network security group.|
|resource\_group|String|True|Extended|The resource group name.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|rules|List|True|Extended|The rules for the security group. See [Table 2](#rules_list).|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

The rules parameter requires a list of rules for the security group. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|access|String|True|Whether network traffic is permitted or denied. Valid values are `Allow` and `Deny`.|
|description|String|False|A description of the rule.|
|destination\_address\_prefix|String|True|The destination CIDR or IP range. You can also specify an asterisk \(`*`\) to match all addresses.|
|destination\_port\_range|String|Y|The destination port or range of ports. You can specify a single port number or a range of ports between 0 and 65535. You can also specify an asterisk \(`*`\) to match all ports.|
|direction|String|True|The direction specifies whether the rule is evaluated on incoming or outgoing traffic. Valid values are `Inbound` and `Outbound`.|
|name|String|False|The name of the rule.|
|priority|Integer|True|The priority of the rule. The value can be between 100 and 4096. The priority number must be unique for each rule in the collection. The lower the priority number, the higher the priority of the rule.|
|protocol|String|True|The network protocol that this rule applies to valid values are `Tcp` and `Udp`.|
|source\_address\_prefix|String|True|The source CIDR or IP range. You can also specify an asterisk \(`*`\) to match all addresses.|
|source\_port\_range|String|True|The source port or range of ports. You can specify a single port number or a range of ports between 0 and 65535. You can also specify an asterisk \(`*`\) to match all ports.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the network security group.|
|network\_security\_group\_id|String|The ID of the network security group.|
|show|String|The details of the network security group.|

## Example

This example creates a network security group with two tags.

```
azure_nsg_1:
    type: IBM::Azure::NetworkSecurityGroup
    properties:
      name: testnsg1
    metadata:
      azure_properties:
        resource_group: cmh-resourcegroup-1
        rules:
          - name: allow-3306
            description: 'my rule 1 for 3306'
            direction: Inbound
            protocol: '*'
            source_address_prefix: '*'
            destination_address_prefix: '*'
            destination_port_range: '*'
            source_port_range: '3306'
            access: Allow
            priority: 201
          - name: rule2
            direction: Inbound
            protocol: 'Tcp'
            source_address_prefix: 'Internet'
            destination_address_prefix: '*'
            access: Deny
            source_port_range: '*'
            destination_port_range: '*'
            priority: 202
        tags:
          tag1 : nsgtag1
          tag2 : nsgtag2
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

