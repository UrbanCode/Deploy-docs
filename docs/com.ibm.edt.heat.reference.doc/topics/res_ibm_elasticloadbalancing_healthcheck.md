# IBM::ElasticLoadBalancing::HealthCheck

This resource type represents the health check function for a load balancer.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|admin\_state\_up|Boolean|False|Core|The administrative state of the health monitor. The default value is `true`.|
|delay|Integer|True|Core|The minimum time in seconds between regular connections of the member.|
|expected\_codes|String|False|Core|The list of HTTP status codes that are expected in response from the member to declare it healthy.|
|healthy\_threshold|Integer|True|Extended|The number of consecutive health probe successes that are required before the instance achieves the Healthy state.|
|http\_method|String|False|Core|The HTTP method that the HTTP monitor type uses for requests.|
|load\_balancer|String|False|Extended|The name of load balancer to apply the health check to.|
|max\_retries|Integer|True|Core|The number of permissible connection failures before the member status is changed to `INACTIVE`.|
|port|Integer|True|Extended|The port number to check.|
|timeout|Integer|True|Core|The maximum number of seconds for a monitor to wait for a connection to be established before it times out.|
|type|String|True|Core|One of the predefined health monitor types. The following values are allowed:-   `PING`
-   `TCP`
-   `HTTP`
-   `HTTPS`

|
|url\_path|String|False|Core|The HTTP path that is used in the HTTP request that the monitor uses to test the health of a member.|

This resource type has no attributes.

**Parent topic:** [Amazon ElasticLoadBalancing resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_elasticloadbalancing_ov.md)

