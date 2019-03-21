# Applying licenses to servers and agents

To use licenses, you install a Rational® Common Licensing server, import your license keys, and link the HCL® UrbanCode™ Deploy servers or agents to the license server.

Ensure that you have a Rational Common Licensing server with licenses for HCL UrbanCode Deploy.

The following Roles and Permissions are needed to assign Licenses to an Agent:

**Web UI:** 

Resources Tab

**Agent:** 

View Agents

Edit Basic Settings

For more information regarding roles and permissions see [Permission reference](../../com.udeploy.admin.doc/topics/security_roles_permission_ref.md#) 

For information about the types of licenses, see [License scenarios](license_scenarios.md).

1.  On the HCL UrbanCode Deploy server, click **Settings** \> **System Settings**.
2.   On the System Settings page, under **Licensing**, specify the connection information for the license server and click **Save**. You can specify the port and host name or IP address for the license server, such as `27000@RCLServer.example.com`. To avoid problems when a license server is not available, you can specify multiple license servers. In this case, separate each address with colons on Linux™ and UNIX™ or semicolons on Windows™, as in the following example: `27000@RCLServer.example.com;27000@backupRCLServer.example.com`. For more complicated license server scenarios, see this document: [http://www-01.ibm.com/support/knowledgecenter/SSSTWP\_8.1.4/com.rational.license.doc/topics/r\_specify\_lic\_servers.html](http://www-01.ibm.com/support/knowledgecenter/SSSTWP_8.1.4/com.rational.license.doc/topics/r_specify_lic_servers.html). For more information about licensing, see [License management](../../com.udeploy.doc/topics/licenseManage.md). The **Server License Type** field shows the type of licensing that the server is using.
3.   If you are using virtual server and managed virtual server \(Server Agent\) licensing, specify whether to assign licenses to the agents automatically or manually. These steps are not necessary for the other types of licensing. 

    -   To assign licenses to agents automatically, set **Automatic Agent Licensing** to **On** and then click **Save**. This setting is meaningful only if you are using virtual server and managed virtual server \(Server Agent\) licensing.
    -   To assign licenses to agents manually, follow these steps:
    1.   Click **Resources** \> **Agents**. 
    2.   Next to an agent, click **Actions** and then click **License**. This menu item is available only if the **Server License Type** field is set to `Server Agent` and **Automatic Agent Licensing** is set to **Off**.
    3.   In the Confirmation window, click **OK**. The **License** column for the agent shows **AUTHORIZED** and the agent is licensed.
    If you are using a license scenario other than virtual server and managed virtual server \(Server Agent\) licensing, the HCL UrbanCode Deploy server assigns licenses to agents automatically. If you are using token licenses or floating licenses, the server attempts to retrieve the necessary license or licenses from the license servers that are available to the HCL UrbanCode Deploy server.

    **Note:** If you provision cloud environments by using the blueprint designer and use virtual server and managed virtual server \(Server Agent\) licensing, configure the server to assign licenses to agents automatically.

4.   Restart the HCL UrbanCode Deploy server. You must restart the server for it to recognize the new type of license.

Now you can run processes on the licensed servers and agents.

**Parent topic:** [License management](../../com.udeploy.doc/topics/licenseManage.md)

