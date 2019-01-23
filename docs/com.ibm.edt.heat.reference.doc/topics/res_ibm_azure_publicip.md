# IBM::Azure::PublicIP

This resource type represents a public IP address on an Microsoft Azure image.

This resource type extends the OpenStack resource type `OS::Neutron::FloatingIP`.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|allocation\_method|String|False|Extended|Defines whether the IP address is static or dynamic. Valid values are `Dynamic` \(the default\) and `Static`.|
|domain\_name\_label|String|False|Extended|The domain name label. The domain name label and regionalized DNS zone make up the FQDN for the public IP address. If a domain name label is specified, a DNS record is created for the public IP in the Azure DNS system.|
|idle\_timeout\_in\_minutes|String|False|Extended|The idle timeout of the public IP address.|
|name|String|True|Extended|The public IP address name.|
|port\_id|String|False|Core|The network interface to associate with this public IP address.|
|region|String|True|Extended|The Azure location. The blueprint designer specifies this property automatically, based on the selected region.|
|resource\_group|String|True|Extended|The resource group name.|
|reverse\_fqdn|String|False|Extended|A user-visible, fully qualified domain name that resolves to this public IP address. If this property is specified, a PTR DNS record is created pointing from the IP address in the `in-addr.arpa` domain to the reverse FQDN.|
|tags|List|False|Extended|A list of name-value pairs to set as tags on the resource.|

|Attribute|Type|Description|
|---------|----|-----------|
|fqdn|String|The fully qualified domain name of the public IP address.|
|name|String|The name of the IP address.|
|public\_ip|String|The public IP address.|
|public\_ip\_address\_id|String|The Azure ID of the IP address.|
|show|String|The details of the public IP address.|

## Example

This example creates a public IP address with a tag and associates it to an existing network interface.

```
  azure_public_ip:
    type: IBM::Azure::PublicIP
    properties:
      port_id: test-azure-nic
    metadata:
      azure_properties:
        resource_group: test-rg
        name: testpublicip1
        tags:
          tag2: iptag
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

