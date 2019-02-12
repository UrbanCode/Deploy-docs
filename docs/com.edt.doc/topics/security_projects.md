# Creating cloud projects for the blueprint designer

A cloud project for the blueprint designer represents a tenant or project on a cloud system. You can give users access to cloud systems through cloud projects.

-   Connect the blueprint design server to a cloud. See [Connecting to clouds through the blueprint designer](security_cloud_connection.md).
-   On that cloud system, create one or more accounts and configure their access. The blueprint designer users use these functional IDs to access the cloud. You can create multiple functional IDs for each cloud and grant the functional IDs appropriate access for each team that you configure on the blueprint designer.
-   If you do not use the Keystone server that was supplied with the engine, create one or more Keystone accounts. You can create one account with all permissions, including creating instances, or you can create separate accounts with different permissions. The accounts must be members of the administrative tenant. If you create one account, you can define access to resources for each team.

    **Note:** If you use the Keystone server that is supplied with engine, you can use the default account on the administrative tenant. The The Keystone server's default administrative tenant user name is `admin` and the default password is `openstack1`.


1.   Log in to the blueprint designer as a user with the following **System** permissions: 
    -   Configure Security
    -   Manage Users & Groups
2.  Click **Settings** \> **Clouds**.
3.   Click **Add New Connection**. 
4.  Specify the following information, depending on the type of cloud: 

    |Property|Description|
    |--------|-----------|
    |**Name \(Project name from OpenStack\)**|For OpenStack Keystone version 3, specify the OpenStack project name. For Keystone version 2, specify the tenant name. If you use the Keystone server that is provided with the engine, the default value is admin.|
    |**Facing Type**|Select the type of URL for the Heat engine.|
    |**Functional ID**|Enter the ID of the functional account on the OpenStack system. If you use the Keystone server that is provided with the engine, the default value is `admin`.|
    |**Password**|Enter the password for the functional account. If you use the Keystone server that is provided with the engine, the default value is `openstack1`.|
    |**Tenant**|Enter the tenant ID to use.|
    |**Domain**|If your OpenStack identity service uses the Identity API v3, enter the domain that the project is on. If you use the Keystone server that is provided with the engine, the default value is `default`.|
    |**Identity URL**|Specify the location of the identity service, such as `http://example.com:5000/v2.0` or `http://example.com:5000/v3`. Do not include a trailing slash.|
    |**Timeout in Mins**|Specify the amount of time in minutes to wait for a provision request to be completed. If you deploy HCL® UrbanCode™ Deploy components, allow sufficient time for the cloud to provision your instance, the agent to come online, and all processes to run. See [Creating a HCL UrbanCode Deploy timeout configuration file](timeout_config.md#).|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the SoftLayer cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**SoftLayer User ID**|Enter the account ID for SoftLayer.|
    |**SoftLayer API Key**|Enter The API key for SoftLayer.|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the Amazon cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**Amazon Access ID**|Enter the ID for AWS.|
    |**Amazon Secret Key**|Enter the password for AWS.|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the VMware vCenter cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**VMware vCenter User ID**|Enter the user ID for VMware vCenter.|
    |**VMware vCenter Password**|Enter the password for VMware vCenter.|
    |**VMware vCenter Host**|Enter the host name of the VMware vSphere API for vCenter server. This is the host name portion of the property `VirtualCenter.VimApiUrl`.|
    |**VMware vCenter Port**|Enter the port of the VMware vSphere API for vCenter server. This is the port portion of the property `VirtualCenter.VimApiUrl`.|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the VMware vRealize cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**VRA User ID**|Enter the user ID for VMware vRealize Automation.|
    |**VRA Password**|Enter the password for VMware vRealize Automation.|
    |**VRA Host**|Enter the URL that hosts the VMware vRealize Automation server.|
    |**VRA Tenant Name**|Enter the tenant name from the VMware vRealize Automation server.|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the Azure cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**Azure Subscription ID**|Enter the subscription ID to use. You can find this information in the Azure web portal or by running the CLI command azure account list.|
    |**Azure Client ID**|Enter the ID of the application to associate the connection with. You can create a temporary application with the azure ad app create command.|
    |**Azure Client Secret**|Enter the password of the application. You specified this password when you created the application with the azure ad app create command.|
    |**Azure Tenant ID**|Enter the tenant ID to use. You can find this information by running the CLI command azure account list.|

    |Property|Description|
    |--------|-----------|
    |**Name**|Specify the name of the Google Cloud Platform cloud project.|
    |**Default Orchestration Service**|Select the orchestration service.|
    |**Upload your Google Cloud credentials**|Upload the file for your Google Cloud service account key that contains your API key credentials. Only JSON key files are supported. See [Creating a key file for Google Cloud Platform](cloud_connect_google_cloud_keyfile.md#).    1.  Click **Choose File**.
    2.  Select the JSON key file on your computer, and click **Open**. The JSON file name is in this format: `service\_account\_name-12\_digits\_of\_its\_private\_key\_id`
|

5.   If your VMware cloud requires NSX networking types, select the **Configure NSX access** check box and specify the following information: 

    |Property|Description|
    |--------|-----------|
    |**NSX User ID**|Enter the NSX user ID.|
    |**NSX Password**|Enter the password for the NSX user ID.|
    |**NSX Host**|Enter the VMWare NSX API host IP address and port number.|

6.  Click **Test Connection** to verify that the connection information is correct.
7.  Click **Save**.

Assign the cloud project to a team:

1.  Click **Teams**, and then select a team.
2.  Go to the **Cloud Authorization** tab, and click **Add**.
3.  Click **Save**.

**Parent topic:** [Setting up access to clouds in the blueprint designer](../../com.edt.doc/topics/security_auth_bds.md)

