# License scenarios

After the evaluation period, you must acquire a license before you can use all product features. Several different license scenarios are available. Depending on the scenario, you might need to apply licenses to HCL® UrbanCode™ Deploy servers, agents, or both.

**Note:** HCL UrbanCode Deploy is also available as a hosted service. In this case, IBM hosts the server for you. For more information, see the [IBM Marketplace](https://www.ibm.com/us-en/marketplace/application-release-automation).

**Important:** Regardless of the license scenario that applies to your environment, each licensed agent requires a connection from each server to the Rational® Common Licensing server. Therefore, the license server must be able to have enough open connections for your topology. The total number of connections to the license server depends on how many agents and servers are running.

For example, if you are using Server Agent licensing and have 1,000 licensed agents and 3 servers, the license server must be able to handle 3,003 simultaneous connections: 1,000 connections from each of the three servers to maintain licenses for the agents, and one connection for each server itself. If you are using floating licenses, the calculations are similar, but only the active agents require connections to the license server.

If you are using the IBM License Metric Tool to monitor license usage, you must ensure that agents are connected to the server so that the correct license usage is reported. The agents get their license type from the connection to the HCL UrbanCode Deploy server. Therefore, if the agents cannot connect to the HCL UrbanCode Deploy server, the .swtag files in the agent directory might be incorrect, and as a result, the license usage reports from the License Metrics Tools might not reflect actual usage. Check firewalls and other agent connectivity issues to be sure that licenses are available and accurately accounted for. For floating licenses, the agent holds a license during the deployment plus the waiting time.

The following license scenarios are available.

**Note:** HCL UrbanCode Deploy does support mixing license types. If more than one of these license types are available on the license server, HCL UrbanCode Deploy uses the type of license with the highest priority. The license scenarios have the following priority, from highest to lowest:

1.  Virtual server and managed virtual server \(Server Agent\) licensing
2.  Processor value unit \(PVU\) licensing
3.  Concurrent sessions \(floating licenses\)
4.  Concurrent sessions \(token licenses\)

For example, if the license server has each type of license, when an HCL UrbanCode Deploy server starts, it retrieves a virtual server and managed server license. If another HCL UrbanCode Deploy server starts and no more licenses of this type are available, that server does not receive a license and does not use the other types of license.

The HCL UrbanCode Deploy server looks for server licenses in the following order of precedence:

1.  Virtual server and managed virtual server \(Server Agent\) licensing
2.  Concurrent sessions \(floating licenses\)
3.  Concurrent sessions \(token licenses\)

If none of these license types are available, the server cannot assign licenses to agents.

If no license can be obtained for the HCL UrbanCode Deploy server or an agent, a warning message appears on the server web interface. The message is shown to all users until an administrator closes it by clicking the close icon within the warning message.

## Virtual server and managed virtual server \(Server Agent\) licensing

In this scenario, the server and agents require separate licenses. You apply the `IBM URBANCODE DEPLOY SERVER AGENT VIRTUAL SERVER` license to the server and `IBM URBANCODE DEPLOY SERVER AGENT MANAGED VIRTUAL SERVER` licenses to the agents. If an agent does not have a license, it cannot run processes.

In this scenario, you can either allow the server to assign licenses to agents automatically or you can assign licenses to agents manually. See [Applying licenses to servers and agents](license_apply.md). The licenses are released when the agents are deleted.

UrbanCode Deploy is configured with a finite number of Server Agent licenses for an organization. When the maximum number of licenses are in use, any additional agents configured will become unlicensed and cannot run processes. Any process run on an unlicensed agent will log an error message. To resolve licensing warnings, additional licenses must be obtained, or existing licenses must be reassigned among the agents.

## Processor value unit \(PVU\) licensing

In this scenario, you apply the `IBM URBANCODE DEPLOY MANAGED CAPACITY PVU LIC` license to the HCL UrbanCode Deploy server. Then, the server can run processes. In this case, the agents do not require a separate license file; instead, each PVU license allows the server to use some agents concurrently. The number of concurrent agents might be limited or unlimited, depending on the terms of the PVU license. If you are using this license scenario and the license server does not have any PVU licenses for an HCL UrbanCode Deploy server, the server cannot run processes.

You can track your use of the PVU licenses with the IBM® License Metric Tool. See [IBM License Metric Tool](http://www-01.ibm.com/support/knowledgecenter/SS8JFY_7.5.0/com.lmt75.doc/ic-homepage_lmt.html).

## Concurrent sessions \(floating licenses\)

In this scenario, the `IBM URBANCODE DEPLOY SESSION PER SIMULTANEOUS SESSION LIC` license is available to the agents. When an agent runs a process, the HCL UrbanCode Deploy server retrieves a license from a license server. If the first license server does not have available licenses, the HCL UrbanCode Deploy server attempts to retrieve a license from the other license servers. Regardless of whether the process succeeds or fails, 15 minutes after the process is complete, the server returns the license to the license server. The same agent that ran the process can reuse that license immediately; however, the license is not available to any other agent until the 15-minute waiting period, also called linger time, is complete.

In this scenario, the HCL UrbanCode Deploy server does not require a separate license.

Although session-based licensing is provided to accommodate fluctuations in application processing demands, peak processing demands result in more requested licenses than available. In order to avoid interruptions in deployments when a license server or servers run out of licenses, the agent is permitted to run the process and an entry is made in the error log. It is the customer's responsibility to monitor session usage and adjust licensing needs as required.

## Concurrent sessions \(token licenses\)

In this scenario, the `IBM URBANCODE DEPLOY SESSION INITIAL TOKEN 2 YEAR` license is available to the agents. When an agent runs a process, the HCL UrbanCode Deploy server retrieves some token licenses from a license server. If the first license server does not have enough available licenses, the HCL UrbanCode Deploy server attempts to retrieve licenses from the other license servers. Each agent requires twenty-two tokens to run a deployment. 15 minutes after the process is complete, the server returns the licenses to the license server. In this scenario, the server does not require a license.

Although session-based licensing is provided to accommodate fluctuations in application processing demands, peak processing demands result in more requested licenses than available. In order to avoid interruptions in deployments when a license server or servers run out of licenses, the agent is permitted to run the process and an entry is made in the error log. It is the customer's responsibility to monitor session usage and adjust licensing needs as required.

## Licenses for use with high-availability servers

If you use a high-availability server configuration, you might require a different license server configuration. See [High-availability options for Rational License Key Server](http://www-01.ibm.com/support/docview.wss?uid=swg27036356).

## Licenses for use with the blueprint design server

The blueprint designer can be used with all HCL UrbanCode Deploy license scenarios and does not require separate or extra licenses. Process requests that you initiate by provisioning a blueprint from the blueprint designer use the same agent licensing rules as requests that you initiate from the server.

## Licensing for upgraded servers

If you upgraded the server from a licensed version 4.8.5, 5.0, or 6.0 to version 6.0.1 or later, the **Server License Type** field is set to `Disabled` until you install a license server and configure a license.

## Licensing for z/OS®

Agents on z/OS use different licensing scenarios than agents on distributed systems. \(Agents on z/Linux™ use the same licensing scenarios as agents on distributed systems.\) Each agent requires a license, even if multiple agents are running on a single LPAR. One agent is required on each environment, even if the environments are on a single sysplex. To run deployments, agents on z/OS must have one of the following licenses:

-   `IBM URBANCODE DEPLOY MANAGED CAPACITY PVU SYS Z LIC`
-   `IBM URBANCODE DEPLOY SERVER AGENT VIRTUAL SERVER SYS Z LIC` and `IBM URBANCODE DEPLOY SERVER AGENT MANAGED VIRTUAL SERVER SYS Z LIC`
-   `IBM URBANCODE DEPLOY SESSION PER SIMULTANEOUS SESSION SYS Z LIC`
-   `IBM URBANCODE DEPLOY AGENT FOR Z/OS WORKLOADS PER MVS LIC`: One license permits one agent to run deployments on z/OS.
-   `IBM URBANCODE DEPLOY SESSION FOR SIMULTANEOUS SESSION FOR Z/OSWORKLOADS LIC`: 155 tokens permit one agent to run deployments on z/OS. As with token licensing on other platforms, the agent retains the tokens for 15 minutes after the deployment is complete.

**Parent topic:** [License management](../../com.udeploy.doc/topics/licenseManage.md)

