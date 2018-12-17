# IBM::ElasticLoadBalancing::LoadBalancer

This resource type represents a load balancer.

The blueprint uses the core properties and extended properties, if any, from this resource type. Review and configure the applicable heat resources that apply to your configuration information.

In the blueprint designer, you can configure the properties that the following table includes. Properties are listed as either “core” or “extended.” Each type of property is located in separate sections of the heat resource that you can view in the blueprint designer. You set the core properties in the properties section and set the extended properties in the metadata section of the blueprint.

|Name|Type|Required|Core or extended|Description|
|----|----|--------|----------------|-----------|
|availablity\_zones|List|False|Extended|A list of availability zones to load balance. You must specify a value for either availability\_zones or subnets.|
|cross\_zone|Boolean|False|Extended|The state of load balancing across multiple availability zones. The default value is false.|
|health\_check|Map|True|Extended|Periodic application health check to confirm availability of the instances.|
|listeners|List|True|Extended|A list of listeners, which are processes that listen for connection requests to attach to the load balancer.|
|members|List|False|Core|The list of Nova server IDs that are load balanced.|
|name|String|True|Extended|The name of the load balancer.|
|pool\_id|String|False|Core|The ID of the load balancing pool.|
|protocol\_port|Integer|False|Core|The port number of the pool members on which the loadbalanced servers run.|
|scheme|String|False|Extended|The load balancer scheme. Specify internal to create an internal load balancer with a DNS name that resolves to private IP addresses or internet-facing to create a load balancer with a publicly resolvable DNS name that resolves to public IP addresses. The default value is internet\_facing|
|security\_groups|List|False|Extended|A list of VPC security groups.|
|subnets|List|False|Extended|A list of subnets to load balance. You must specify a value for either availability\_zones or subnets.|

The health\_check parameter requires a map of threshold properties. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|healthy\_threshold|Integer|True|Specifies the number of consecutive health probe successes that are required before moving the instance to the Healthy state.|
|interval|Integer|True|Specifies the approximate interval, in seconds, between health checks of an individual instance.|
|target|String|True|Specifies the instance's protocol and port to check. The following protocol values are allowed: -   `TCP`
-   `HTTP`
-   `HTTPS`
-   `SSL`

 The range of valid ports is 1 - 65535.**Note:** 

For TCP and SSL, you specify a port pair. For example, you can specify `TCP:5000` or `SSL:5000`. The health check attempts to open a TCP or SSL connection to the instance on the port that you specify. If the health check fails to connect within the configured timeout period, the instance is considered unhealthy.

For HTTP or HTTPS, you specify a port and a path to ping \(HTTP or HTTPS:port/PathtoPing\). For example, you can specify `HTTP:80/weather/us/wa/seattle`. In this case, an HTTP GET request is issued to the instance on the specified port and path. If the health check receives any response other than `200 OK` within the configured timeout period, the instance is considered unhealthy. The total length of the HTTP or HTTPS ping target cannot be more than 1024 16-bit Unicode characters.

|
|timeout|Integer|True|Specifies the amount of time, in seconds, during which no response means a failed health probe. This value must be less than the value for Interval.|
|unhealthy\_threshold|Integer|True|Specifies the number of consecutive health probe failures that are required before moving the instance to the Unhealthy state.|

The listeners parameter requires a list of ports. The following table shows the properties in each list item.

|Property|Type|Required|Description|
|--------|----|--------|-----------|
|instance\_port|Integer|True|Specifies the TCP port on which the instance server is listening.|
|instance\_protocol|String|False|Specifies the protocol to use for routing traffic to back-end instances. The following values are allowed: -   `TCP`
-   `HTTP`
-   `HTTPS`
-   `SSL`

**Note:** 

If the front-end protocol is HTTP or HTTPS, instance\_protocol must be at the same protocol layer. Likewise, if the front-end protocol is TCP or SSL, instance\_protocol must be TCP or SSL.

If there is another listener with the same instance\_port whose instance\_protocol is secure, for example HTTPS or SSL, the listener's instance\_protocol must be secure, for example HTTPS or SSL. If there is another listener with the same instance\_port whose instance\_protocol is HTTP or TCP, the listener's instance\_protocol must be either HTTP or TCP.

|
|load\_balancer\_port|Integer|True|Specifies the external load balancer port number.|
|protocol|String|True|Specifies the load balancer transport protocol to use for routing. The following values are allowed: -   `TCP`
-   `HTTP`
-   `HTTPS`
-   `SSL`

|
|ssl\_certificate\_id|String|False|The ARN of the SSL certificate to use. For more information about SSL certificates, see [Managing Server Certificates](http://docs.aws.amazon.com/IAM/latest/UserGuide/ManagingServerCerts.html) in the AWS Identity and Access Management documentation.|

|Name|Description|
|----|-----------|
|dns\_name|The DNS name for the load balancer.|

**Parent topic:** [Amazon ElasticLoadBalancing resource types](../../com.ibm.edt.heat.reference.doc/topics/ref_heat_types_elasticloadbalancing_ov.md)

