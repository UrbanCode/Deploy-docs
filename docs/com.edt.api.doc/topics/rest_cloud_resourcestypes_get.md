# List the resource types on the cloud

This command is equivalent to the command "heat resource-type-list."

## Request

```
GET http://{hostname}:{port}
  /landscaper/rest/cloud/resourcesTypes
Accept: application/json

```

|Parameter|Type|Required|Description|
|---------|----|--------|-----------|
|Accept|`application/json`|true| |
|useMockData|boolean|false| |

## Example

```
curl -u jsmith:passwd 
  http://myserver.example.com:8080/landscaper/rest/cloud/resourcesTypes
```

## Example response

```
[
    "AWS::EC2::Instance",
    "IBM::EC2::InternetGateway",
    "AWS::EC2::NetworkInterface",
    "OS::Heat::ScalingPolicy",
    "AWS::CloudFormation::Stack",
    "IBM::EC2::EIPAssociation",
    "AWS::EC2::Volume",
    "OS::Neutron::IPsecPolicy",
    "OS::Heat::SoftwareDeployment",
    "IBM::EC2::Volume",
    "AWS::AutoScaling::ScalingPolicy",
    "OS::Neutron::HealthMonitor",
    "AWS::IAM::User",
    "OS::Neutron::LoadBalancer",
    "AWS::EC2::InternetGateway",
    "IBM::UrbanCode::SoftwareDeploy::UCD",
    "OS::Neutron::FloatingIP",
    "IBM::EC2::RouteTableAssociation",
    "OS::Neutron::RouterGateway",
    "AWS::EC2::SubnetRouteTableAssociation",
    "AWS::EC2::VolumeAttachment",
    "AWS::CloudFormation::WaitConditionHandle",
    "OS::Cinder::VolumeAttachment",
    "OS::Neutron::FirewallRule",
    "IBM::EC2::VolumeAttachment",
    "OS::Heat::CWLiteAlarm",
    "IBM::UrbanCode::ResourceTree",
    "OS::Nova::FloatingIP",
    "OS::Trove::Instance",
    "OS::Ceilometer::CombinationAlarm",
    "OS::Neutron::MeteringLabel",
    "IBM::EC2::EIP",
    "OS::Neutron::SecurityGroup",
    "OS::Heat::InstanceGroup",
    "AWS::AutoScaling::AutoScalingGroup",
    "OS::Heat::AutoScalingGroup",
    "OS::Heat::CloudConfig",
    "OS::Neutron::PoolMember",
    "AWS::EC2::SecurityGroup",
    "OS::Ceilometer::Alarm",
    "OS::Neutron::Router",
    "OS::Neutron::IKEPolicy",
    "AWS::EC2::VPC",
    "OS::Cinder::Volume",
    "OS::Heat::SoftwareConfig",
    "AWS::EC2::VPCGatewayAttachment",
    "AWS::CloudFormation::WaitCondition",
    "AWS::S3::Bucket",
    "IBM::EC2::Server",
    "OS::Neutron::FirewallPolicy",
    "AWS::EC2::RouteTable",
    "OS::Neutron::Port",
    "OS::Heat::RandomString",
    "AWS::EC2::Subnet",
    "OS::Heat::HARestarter",
    "OS::Nova::KeyPair",
    "IBM::EC2::RouteTable",
    "OS::Neutron::ProviderNet",
    "OS::Heat::MultipartMime",
    "OS::Heat::UpdateWaitConditionHandle",
    "OS::Nova::Server",
    "AWS::IAM::AccessKey",
    "IBM::EC2::Subnet",
    "OS::Neutron::FloatingIPAssociation",
    "OS::Neutron::Net",
    "IBM::EC2::VPC",
    "AWS::EC2::EIPAssociation",
    "OS::Neutron::NetworkGateway",
    "OS::Neutron::Firewall",
    "IBM::UrbanCode::SoftwareConfig::UCD",
    "AWS::EC2::EIP",
    "OS::Heat::AccessPolicy",
    "OS::Heat::StructuredDeployment",
    "AWS::RDS::DBInstance",
    "OS::Neutron::MeteringRule",
    "OS::Swift::Container",
    "AWS::AutoScaling::LaunchConfiguration",
    "IBM::EC2::Port",
    "OS::Nova::FloatingIPAssociation",
    "OS::Heat::ResourceGroup",
    "OS::Neutron::VPNService",
    "OS::Neutron::IPsecSiteConnection",
    "OS::Neutron::Subnet",
    "AWS::ElasticLoadBalancing::LoadBalancer",
    "OS::Neutron::Pool",
    "OS::Neutron::RouterInterface",
    "OS::Heat::StructuredConfig"
]
```

**Parent topic:** [rest/cloud resource](../../com.edt.api.doc/topics/rest_cloud.md)

