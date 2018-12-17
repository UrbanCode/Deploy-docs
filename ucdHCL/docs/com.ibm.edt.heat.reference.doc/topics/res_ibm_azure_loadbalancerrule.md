# IBM::Azure::LoadBalancingRule

This type represents a Microsoft™ Azure load balancing rule. It can create a load balancing rule for a load balancer.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|backend\_address\_pool|String|True|Core|The name or ID of the backend address pool for the load balancing rule.|
|backend\_port|Integer|True|Core|The port for the internal endpoint. The value must be between 1 and 65534.|
|enable\_floating\_ip|Boolean|False|Core|Configures a virtual machine's endpoint for the floating IP capability that is required for configuring a SQL AlwaysOn Availability Group.|
|frontend\_ip\_configuration|String|True|Core|The name or ID of the front-end IP configuration for the load balancing rule.|
|frontend\_port|Integer|True|Core|The port for the external endpoint. Port numbers for each rule must be unique within the load balancer, and the value must be between 1 and 65534.|
|idle\_timeout|Integer|False|Core|Timeout, in minutes, for the TCP idle connection. The default is `4` minutes, and the value must be between 4 and 30 minutes.|
|load\_balancer|String|True|Core|The name of the load balancer to add the load balancing rule to.|
|load\_distribution|String|False|Core|The load distribution policy for the rule. Valid values are:-   `Default`
-   `SourceIP`
-   `SourceIPProtocol`

|
|name|String|True|Core|The name of the load balancing rule.|
|probe|String|True|Core|The ID of the problem for the load balancing rule.|
|protocol|String|True|Core|The transport protocol for the external endpoint. Valid values are `Udp` and `Tcp`.|
|resource\_group|String|True|Core|The resource group name.|

|Attribute|Type|Description|
|---------|----|-----------|
|name|String|The name of the load balancing rule.|
|load\_balancing\_rule\_id|String|The Azure ID of the load balancing rule.|
|show|String|The details of the load balancing rule.|

## Example

This example creates a load balancing rule and associates it with a load balancer:

```
 azure_lb_rule:
    type: IBM::Azure::LoadBalancingRule
    properties:
      name: test-lbrule-1
      resource_group: test-rg
      load_balancer: test-lb
      frontend_ip_configuration: LoadBalancerFrontEnd
      backend_address_pool: testpool
      frontend_port: 8080
      backend_port: 80
      protocol: Tcp
      probe: testprobe
      load_distribution: SourceIP
        
```

**Parent topic:** [Microsoft Azure resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_azure_ov.md)

