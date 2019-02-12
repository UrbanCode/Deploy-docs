# Modeling DNS records with Amazon Route 53

DNS \(domain name service\) records refer host names such as `www.example.com` to IP addresses. Amazon Route 53 can manage DNS records for your domains.

Register a domain name with Amazon AWS or forward your domain to the Route 53 system. Amazon Route 53 is the only DNS provider that is supported. For more information, see [http://aws.amazon.com/route53/](http://aws.amazon.com/route53/).

1.   In the blueprint designer, in the source code of a blueprint, create a hosted zone to contain the DNS records for your domain and specify the domain name. For a public zone, specify only the domain name, as in this example:

    ```
    my-public-zone:
      type: IBM::Route53::HostedZone
      properties:
        name: www.example.com
    ```

2.  To make the zone private, specify the VPC and region for the zone.In this case, the domain referral works only within the specified VPC. For example, the following private zone provides domain referral only to the VPC with the ID `vpc-123456`.

    ```
    my-private-zone:
      type: IBM::Route53::HostedZone
      properties:
        name: www.example.com
        private_zone: True
        vpc_id: vpc-123456
        vpc_region: us-east-1
    ```

3.  Add one or more record sets to the zone.The record set specifies the name of the domain and the target IP addresses. For example, this record set forwards requests for the domain `a.example.com` to the IP addresses `10.8.8.8` and `10.9.9.9`.

    ```
    simple-record-set:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        ttl: 1800
        type: A
        hosted_zone: example.com.
        resource_records:
          10.8.8.8
          10.9.9.9
    ```

4.  To balance traffic between IP addresses, provide weight information and unique identifiers for the record sets.The weight information is relative to all of the record sets for the domain. For example, if you have two record sets with weights of 1 and 2, the record set with the weight of 1 gets one-third of the traffic. This code shows two record sets that are balanced in this way:

    ```
    weighted-record-set-a:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        identifier: weighted-record-set-a
        weight: 1
        type: A
        hosted_zone: example.com.
        resource_records:
          10.8.8.8
    
    weighted-record-set-b:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        identifier: weighted-record-set-b
        weight: 2
        type: A
        hosted_zone: example.com.
        resource_records:
          10.9.9.9
    ```

5.  To direct traffic to different IP addresses based on location, add the region property and provide unique identifiers for the record sets.For example, this code sends traffic from the region `us-east-1` to one IP address and traffic from the region `us-west-1` to a different IP address.

    ```
    latency-record-set-a:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        identifier: latency-record-set-a
        region: us-east-1
        type: A
        hosted_zone: example.com.
        resource_records:
          10.8.8.8
    
    latency-record-set-b:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        identifier: latency-record-set-b
        region: us-west-1
        type: A
        hosted_zone: example.com.
        resource_records:
          10.9.9.9
    ```

6.  Use the record sets to forward traffic from your domain to your servers.For example, the following code creates a record set that forwards the domain `www.example.com` to the dynamic location of the virtual image `my-server`. In this case, the resource\_records property of the record set uses the IP address of the image by referring to the public\_ip\_address property.

    ```
    my-public-zone:
      type: IBM::Route53::HostedZone
      properties:
        name: www.example.com
        
    my-server:
      type: OS:Nova::Server
      properties:
        name: "My server"
        image: "my_image"
        flavor: { get_param: flavor }
        key_name: { get_param: key_name }
        availability_zone: { get_param: availability_zone }
        networks:
          - port: { get_resource: my_port }
        
    my-record-set:
      type: IBM::Route53::RecordSet
      properties:
        name: www.example.com
        type: A
        hosted_zone: example.com.
        resource_records:
          - { get_attr: [my-server, public_ip_address] }
    ```


**Parent topic:** [Modeling software services](../../com.edt.doc/topics/blueprint_service_ov.md)

