# Configuring VMware vCenter image flavors

Flavors represent the capacity of images, including memory, storage space, and processor capacity. You must configure a set of flavors for VMware vCenter.

Configure the cloud discovery service. See [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.ibm.udeploy.doc/topics/cds_configure.md).

After you configure flavors, you can select a flavor at provisioning time to specify the size of the environment.

1.   Open the cloud discovery service configuration file. If you do not have a cloud discovery service configuration file, see [Setting up images, regions, and flavors for the cloud discovery service and engine](../../com.ibm.udeploy.doc/topics/cds_configure.md).
2.  In the section of this file that is labeled `vcenter`, add flavors.Each flavor has the following parameters:

    -   **flavor**

        The name of the flavor. This name appears in the list of flavors when you provision the environment.

    -   **memory**

        The amount of memory in megabytes.

    -   **disk**

        The size of the storage in gigabytes.

    -   **vcpu**

        The number of virtual CPUs.

    For example, the following code creates five flavors:

    ```
    "vcenter": {
        "flavors": [
            {
                "flavor": "m1.tiny",
                "memory": 512,
                "disk": 20,
                "vcpu": 1
            },
            {
                "flavor": "m1.small",
                "memory": 2048,
                "disk": 20,
                "vcpu": 2
            },
            {
                "flavor": "m1.medium",
                "memory": 4096,
                "disk": 40,
                "vcpu": 2
            },
            {
                "flavor": "m1.large",
                "memory": 8192,
                "disk": 80,
                "vcpu": 4
            },
            {
                "flavor": "m1.xlarge",
                "memory": 16384,
                "disk": 100,
                "vcpu": 8
            }
        ]
    }
    ```

3.   Save the file and restart the cloud discovery service. To restart the cloud discovery service, see [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md) and [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/stop_patterns.md).
4.   On the system that hosts the engine, open the /usr/lib/heat/ibm-cloud-ext/resources/ibm-cloud-discovery.conf file. 
5.   In this file, add the same flavors to the `[vmware]` section. For example, the following code contains five flavors that match the flavors in the previous example:

    ```
    [vcenter]
    flavors: [
        {
            "flavor": "m1.tiny",
            "memory": 512,
            "disk": 20,
            "vcpu": 1
        }, {
            "flavor": "m1.small",
            "memory": 2048,
            "disk": 20,
            "vcpu": 2
        }, {
            "flavor": "m1.medium",
            "memory": 4096,
            "disk": 40,
            "vcpu": 2
        }, {
            "flavor": "m1.large",
            "memory": 8192,
            "disk": 80,
            "vcpu": 4
        }, {
            "flavor": "m1.xlarge",
            "memory": 16384,
            "disk": 100,
            "vcpu": 8
        }]
    ```

6.   Save the file and restart the engine. 

Now when you provision environments, the flavors are listed in the **Flavor** list under **Image Parameters**.

**Parent topic:** [Connecting to VMware vCenter v5.5 to 6.0](../../com.ibm.edt.doc/topics/cloud_connect_vmware.md)

