# Troubleshooting agent connections

You can answer a number of questions to help isolate the issue behind problems with agents.

By default, the logs for the agent are in the folder agent\_install/var/log.

If you are having trouble with an agent, see the following troubleshooting information for the state of the agent:

-   [A new agent isn't displayed in the user interface, or the agent is reported as offline](#agent_no_show).
-   [The agent is reported as connecting](#agent_connecting).
-   [The agent is reported as online](#agent_online).
-   [The agent cannot connect to the server](#clock_skew)

**If the agent isn't displayed in the user interface, or if the agent is reported as offline, complete these actions:**

-   Verify that the agent started successfully:
    -   Look for error messages in the log. If the agent started successfully, the agent.out file has a message that says something like this:

        ```
        2017-07-18 08:37:47,575 INFO  AgentWorkerThread com.urbancode.air.agent.AgentWorker - Agent started
        ```

    -   Check the prerequisites for the agent. See [Installing agents](../../com.ibm.udeploy.install.doc/topics/agent_install_ov.md).
    -   If the agent prompt returns right away or the window flashes and closes after you try to start it, check the Java version and Java home. This situation typically happens when Java cannot be found.
    -   Verify that the system that hosts the agent has enough free disk space, and that the file system and permissions are properly configured.
    -   If the agent is configured as a service on Linux, start the agent from the command line. If you cannot start the agent from the command line, the problem is likely related to the way that the service was configured. See [Running agents as services on Linux](../../com.ibm.udeploy.install.doc/topics/agent_install_service.md#).
    -   Verify that the agent installation properties are correct. See [Agent installation properties](../../com.ibm.udeploy.install.doc/topics/agent_properties.md).
    -   If the agent is configured as a service on Windows, complete these actions:
        1.  Remove the service and add it again. See step 5d in [Changing or updating the JRE of agents](jre_change_agent.md#del_add_agent_svc).
        2.  Remove the service and try to start the agent from the command line. If it starts, check permissions for the user who is running the service. See step 3 of [Installing agents from the command line](../../com.ibm.udeploy.install.doc/topics/agentInstall.md#rmv_svc).
    -   If the information that is displayed in the log file or shell or command window doesn't continue beyond the following two example lines, a Java Message Service \(JMS\) communication issue exists:

        ```
        2016-06-24 12:05:21,766 INFO com.urbancode.air.agent.AgentWorker - Logging configured
         2016-06-24 12:05:21,789 INFO com.urbancode.air.agent.AgentWorker - Agent version: 6.1.1.4.665694
        ```

        To resolve this issue, complete these steps:

        1.  Use Telnet to connect to the JMS port: `telnet server\_name/agent\_relay port`.
        2.  If the agent was configured to connect to a host name rather than an IP address, verify that the host name resolves correctly. In some cases where the agent didn't resolve correctly, adding the host and IP address to the /etc/hosts file resolved the issue.
-   If the agent started successfully but the server shows the agent as offline or does not show the agent at all, check these things:
    -   If the agent connects through an agent relay, verify that the relay is running.
    -   Verify that the system that hosts the server has enough free disk space, and that the file system and permissions are properly configured.
    -   Search the user interface for the agent endpoint ID from the installed.properties file. If an agent with the same name is already in the system \(in the following example, see `agent1` in bold\), HCL® UrbanCode™ Deploy adds the agent to the user interface as agent-<agent id\>. It is possible that the agent is there, but not by a name that you might be looking for. This can happen if you clone a virtual machine or create a cloud environment without changing the agent name.

        ```
        #Wed, 20 May 2015 15:41:27 -0500
        #Wed Feb 05 12:19:15 CST 2014
        IBM\ UrbanCode\ Deploy/java.home=C\:\\IBM\\Java70SDK
        locked/agent.brokerUrl=failover\:(ah3\://localhost\:7918)
        locked/agent.home=C\:\\IBM\\ucd\\agent1
        locked/agent.http.proxy.host=
        locked/agent.http.proxy.port=
        **locked/agent.id=P6km5J6GxzCxVbUkM7kP**
        locked/agent.jms.remote.host=localhost
        locked/agent.jms.remote.port=7918
        locked/agent.keystore=../conf/ibm-ucd.keystore
        locked/agent.keystore.pwd=pbe{026vXYdcSWEUXdpiBUi7bXkCWz2JoBVnHnXa1bkbEUs\=}
        locked/agent.mutual_auth=false
        locked/agent.name=agent1
        system.default.encoding=Cp1252
        agent.HttpFailoverHandler.disabled=null
        ```

    -   If the agent is using failover, make sure that failover is configured correctly.
    -   If you are using mutual authentication, verify that it is set up correctly and check for certificate errors.
    -   Check for licensing issues.
    -   Check the network connection between the agent and the server or between the agent and agent relay:
        -   Verify that a firewall is not preventing the agent from connecting to the server or agent relay. Agents always initiate connections to servers and agent relays, not the other way around.
        -   Check to see that the agent system can ping the HCL UrbanCode Deploy server or agent relay.
        -   If agents are not connecting correctly on high-availability environments, make sure that the servers have cluster connections to each other.
        -   Firewalls might prevent the agent from communicating with the server, particularly if the agent is on a public cloud and trying to connect to an HCL UrbanCode Deploy server that is within a firewall. In this case, use an agent relay.
        -   If the agent is on a cloud environment and the target cloud environment can connect to the HCL UrbanCode Deploy server, log in to the cloud image and check the `cloud-init` log files in this folder:/var/lib/cloud/instance/.
        -   If an agent on a cloud environment times out with a message like `Agent did not come online after 6.0 minutes! Process not executed.`, check to see that the agent package was downloaded correctly. If it did, try lengthening the timeout by increasing the value of the agent\_timeout parameter in the blueprint or configuration file.
        -   Check for DNS issues that might prevent the agent from resolving the host name of the server or agent relay.
    -   Can the built-in admin ID see the agent online? If so, permissions might be incorrectly configured on the agent. Remember that the built-in admin ID bypasses the team's checking.

If you do not know the location of the agent that cannot connect to the server, go to the agent properties, which include the last known host name and IP address of the agent.

**If the agent is reported as connecting, complete these actions:**

1.  When this situation occurs, the problem is an HTTP communication issue. To resolve this issue:
    1.  Check the external agent URL in settings. In the product, click **Settings**, and then click **System Settings**. Make sure that the host name or IP address matches or resolves to the entry in the agents installed.property file.
    2.  Use Telnet to connect to the HTTP port on the Server.

**If the agent is reported as online but you continue to have problems, complete these actions:**

1.  Verify that the agent and agent relay are running the recommended and minimum versions as indicated in the user interface.
2.  Check the server, agent relay, and agent logs for errors. Look for matching time stamps among the logs.
3.  Enable more detailed logging by inserting these lines in the agent\_install/conf/agent/log4j file:

    ```
    log4j.logger.com.urbancode.air=TRACE
    ```

    ```
    log4j.logger.org.apache.activemq=TRACE
    ```

    Check the output for errors.


**If you cannot connect server to an agent and the agent receives a clock skew exception, complete these actions:**

Set the system time on the server and the computers that agents are running on to times that are the same or within a few minutes of each other. The server and agent clock times must be close together if using end-to-end encryption. They do not need to be in the same time zone, but must agree about the global time within approximately 5 minutes.

**Parent topic:** [Troubleshooting the HCL UrbanCode Deploy server and agents](../topics/trouble_serveragents_ov.md)

