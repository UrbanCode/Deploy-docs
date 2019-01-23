# Creating an orchestration service with the blueprint designer

You can create orchestration services and connect non-OpenStack clouds, such as Amazon Web Services, SoftLayer, VMware, Azure, and Google Cloud.

You create orchestration services to connect to standalone Heat engines \(non-OpenStack clouds\). To connect to an OpenStack cloud, you only need to add an OpenStack cloud from the **Clouds** tab, as OpenStack uses its own engine.

1.   Click **Settings** \> **Orchestrations**, and then click **Add New Service**. 
2.   Specify the following information: 

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify a name for the orchestration service.|
    |**Identity URL**|Specify the location of the identity service, such as `http://example.com:5000/v2.0` or `http://example.com:5000/v3`. Do not include a trailing slash.|
    |**Timeout in Minutes**|Specify the amount of time in minutes to wait for a provision request to be completed. If you deploy HCL® UrbanCode™ Deploy components, allow sufficient time for the cloud to provision your instance, the agent to come online, and all processes to run. See [Creating a HCL UrbanCode Deploy timeout configuration file](timeout_config.md#).|
    |**Domain**|If your OpenStack identity service uses the Identity API v3, enter the domain that the project is on. If you use the Keystone server that is provided with the engine, the default value is `default`.|
    |**Functional Username**|Enter the ID of the functional account on the OpenStack system. If you use the Keystone server that is provided with the engine, the default value is `admin`.|
    |**Functional Password**|Enter the password for the functional account. If you use the Keystone server that is provided with the engine, the default value is `openstack1`. Do not include a trailing slash.|
    |**Tenant**|Enter the tenant ID to use.|
    |**Orchestration Engine URL**|Specify the location of your engine, such as `http://engine.example.com:8004`.|


**Parent topic:** [Configuring security for the blueprint design server](../../com.ibm.edt.doc/topics/security_ov.md)

