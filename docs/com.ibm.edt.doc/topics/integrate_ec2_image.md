# Registering Amazon EC2 images with the cloud discovery service

To use the blueprint designer to model environments on Amazon Web Services, you must register Amazon Elastic Compute Cloud \(EC2\) images with the cloud discovery service. EC2 is part of AWS. EC2 provides the virtual nodes in an environment, and other services in AWS provide services such as networking and data storage.

Before you register images, configure the cloud discovery service. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.ibm.udeploy.doc/topics/cds_configure.md).

1.   From the EC2 web console, find the ID of the image to register. Image IDs start with `ami-`, such as `ami-abcd1234`. You can register virtual images that use a Linux™ or Windows™ operating system.
2.   Open the cloud discovery service configuration file in a text editor. 
3.   In the `amazon` section, find the region for the image, such as `us-east-1`. 
4.   In the `images` section, add the image ID to the list of images. For example, the following code from a configuration file includes three image IDs in the `us-east-1` region.

    ```
    "amazon": {
      "regions": [
        {
          "id": "us-east-1",
          "name": "US East (Northern Virginia)",
          "images": [
            "ami-abcd1234",
            "ami-1234abcd",
            "ami-5678abcd"
    
          ]
        }
      ]
    },
    ```

5.   In the `images` section, configure images names that contain asterisks \(\*\) as wildcards. All images that match the name pattern that you specify are displayed in the **Images** palette of the blueprint designer. For example, the following code from a configuration file includes three specific image IDs and five image name patterns in the `us-east-1` region.

    ```
    "amazon": {
      "regions": [
        {
          "id": "us-east-1",
          "name": "US East (Northern Virginia)",
          "images": [
            "ami-abcd1234",
            "ami-1234abcd",
            "ami-5678abcd"
            "name:RHEL-*HVM*-20*-GP2",
            "name:suse-sles-12-sp*v20*hvm-ssd-x86_64*",
            "name:suse-sles-11-sp4*v20*hvm-ssd-x86_64*",
            "name:ubuntu/images/hvm-ssd/ubuntu-*-amd64-server-2016*",
            "name:Windows_Server-20*English-64Bit-Base-2016*"
          ]
        }
      ]
    },
    ```

6.   Save the cloud discovery service configuration file. 
7.   Register the EC2 instance types that you provision with the cloud discovery service. 
    1.   Back up the /usr/lib/python2.7/site-packages/clouddiscoveryservice/resources/clouds/instance\_type\_details.py file. For example, you might create a copy of the file and name it instance\_type\_details.py.old.
    2.   Open the instance\_type\_details.py file. 
    3.   Find the region to customize, such as `us-east-1`. 
    4.   In the `REGION_DETAILS` section, add the instance type IDs that you provision to the `instance_types` section for each region. To review the list of available EC2 instance types, see [Amazon EC2 Instance Types](https://aws.amazon.com/ec2/instance-types/). For example, the following code from the instance\_type\_details.py file includes three instance types in the `us-east-1` region.

        ```
        REGION_DETAILS = {
            # US East (Northern Virginia) Region
            'us-east-1': {
                'endpoint': 'ec2.us-east-1.amazonaws.com',
                'api_name': 'ec2_us_east',
                'country': 'USA',
                'signature_version': '2',
                'instance_types': [
                    't2.micro',
                    'm3.medium',
                    'm4.large'   
                ]
            }
        }
        ```

    5.   In the `INSTANCE_TYPES` section, add the details for each instance type. Contact AWS support to obtain the instance type details. For example, the following code from the instance\_type\_details.py file includes details for the `t2.micro`, `m3.medium`, and `m4.large` instance types that are shown in the `us-east-1` region.

        ```
        INSTANCE_TYPES = {
            't2.micro': {
                'id': 't2.micro',
                'name': 't2.micro (Burstable Performance Micro Instance)',
                'ram': 1024,
                'disk': 0,  # EBS Only
                'bandwidth': None,
                'extra': {
                    'cpu': 1
                }
            },
            'm3.medium': {
                'id': 'm3.medium',
                'name': 'm3.medium (Medium Instance)',
                'ram': 3840,
                'disk': 4000,
                'bandwidth': None
            },
            'm4.large': {
                'id': 'm4.large',
                'name': 'm4.large (Large Instance)',
                'ram': 8192,
                'disk': 32000,
                'bandwidth': None
            }
        }
        ```

8.   Save the instance\_type\_details.py file. 
9.   Restart the cloud discovery service. To restart the cloud discovery service, see [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md).

**Parent topic:** [Connecting to Amazon Web Services](../../com.ibm.edt.doc/topics/cloud_connect_amazon.md)

