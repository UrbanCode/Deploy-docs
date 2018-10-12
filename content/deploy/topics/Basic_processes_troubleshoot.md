# Troubleshooting processes {#reference_id_proc_probs .reference}

You can answer a number of questions to help isolate the issue behind problems and process failures.

Take these initial approaches to avoid problems with your processes and check these areas before you take more complicated troubleshooting steps:

-   If a process is failing, look for information about the failure in the process request. To open a process request, click the application, and go to the **History** tab. Find the process in the table, and click **View Request**. Within the request, expand the steps until you find the step that failed. Failed steps have an error log ![](../images/steperrorlog.gif) that provides more information about the failure. All steps have an output log ![](../images/steplog.gif) that includes information about the step progress and any logging messages that the step created. For information about viewing logs, see [Viewing logs](log_audit.md#).
-   Step through each process element. Verify that you [refer to properties](ud_properties_using.md#) by using the correct syntax.
-   Verify that the steps are wired together, meaning that each step is connected to another step within a process. Then, verify that the correct step result is selected. That is, on the arrow that connects one step with the next, select the correct condition for proceeding: **Run On Success**, **Run On Failure**, or **Run on Both**.
-   Verify that the process is wired in to the **Finish** step.
-   Consider running each process step's equivalent function in a command-line environment to verify that each step works as planned. For example, if the step runs a shell script, try running the shell script on the command line to see whether the same problem happens. If the step starts an application server, make sure that you can start the application server on the command line by using the same commands.
-   Verify that you are using the correct component processes type. For information about component process types, see [Component process types](comp_process_types.md#).
-   Trace all the way through your process step-by-step. Steps are essentially commands to be run. See this IBM support article: [MustGather: How to trace the execution of a process](http://www-01.ibm.com/support/docview.wss?uid=swg21653769).
-   Verify that no typographical errors are included in the process steps. Review each property and script carefully.
-   If properties are a factor in the problem, you can view the properties for an application process by opening the process request and clicking the **Properties** tab. You can also view the properties that each component process step used by clicking **Input/Output Properties** ![](../images/viewproperties.gif). For more information about properties, see [Properties](ud_properties_overview.md#) and associated topics.
-   Check the log for messages that pertain to memory size. You can generate a report of requirements for your operating systems and product version: [Hardware requirements for a specific product](http://www-969.ibm.com/software/reports/compatibility/clarity/hardwareReqsForProduct.html).
-   If you are running a UNIX™ based operating system, are your file handles configured correctly according to the [documentation](../../com.ibm.udeploy.install.doc/topics/sysRequire.md#file_handles)?
-   If you are using sudo commands, permissions can be a problem. Verify that the command is configured correctly. Also, verify that the user is configured in sudo and does not need to specify a password. Make sure that the directory can be accessed by the operating system user that is running the IBM UrbanCode Deploy agent, the impersonated user, and the tool that you are calling. For information about sudo commands, see [Impersonation on Linux™ systems](arch_appx_sudo_using.md#).
-   Review the step output for steps that cause problems. On a command line, run a problem line or step as the same user that IBM UrbanCode Deploy uses to run the step or line. Be sure to pass the user and the group.

## Other troubleshooting tips { .section}

-   If your process branches, look closely at the way the process branches to ensure that the process is running in the way that you expect. See [Branching and joining steps](comp_process_join.md).
-   If the agent does not respond to server requests quickly enough because of performance problems or network issues, the server adds an output property to the step. This property is named `ackTimeout` and the value is `The step has timed out because the agent did not respond with an acknowledgement within the specified time.` To extend the time that the server waits, add the following line to the server installed.properties file:

    ```
    com.urbancode.ds.plugin.PluginAckTimeoutRunnable.TIMEOUT_INTERVAL=3600000 
    ```


## What issues are you observing or experiencing? { .section}

-   [A process doesn't start](#procss_no_start).
-   [A process fails, but no errors are logged](#fail-no_log).
-   [Process failures occur after an upgrade](#fail_after_upgrade).
-   [A process runs, but it does not stop](#run_no_stop).
-   [Processes fail intermittently](#proc_fail_intermitt).
-   [Processes stop before completion](#proc_hang).
-   [Processes with branches do not run correctly](#branch_probs).
-   [Processes using impersonation do not run correctly](#impersonation_probs).

**A process doesn't start**

-   Can you run the process while you use the built-in ID? Running the process that way checks for a permission issue on the resource.
-   Is the agent running? For information about agents, see [Agents](resources_agents.md#).
-   Can any processes run on the agent? If required, create a simple “echo Hello World” shell step, and see whether you can run it on the agent. Running this shell step confirms that communication between the server and resource are established.
    -   If the simple shell step works, what's different between the working step and the failing step?
-   Are the components mapped? See [Mapping resources and components to environments](app_environment_mapping.md#).
-   Are any errors logged in the step output? See [Viewing logs](log_audit.md#).
-   Check the server log file for errors, permissions issues, or configuration issues. See [Viewing logs](log_audit.md#).

**A process fails, but no errors are logged**

-   Confirm that the version of IBM UrbanCode Deploy and the agents and agent relays are the same.
-   Check the agent log file for errors that point to a configuration issue. For example, a port might be blocked or a URL is incorrect. Check the server log file for errors. For example, a port might be blocked or URL is incorrect. See [Viewing logs](log_audit.md#). See also [Firewall and communication configuration](../../com.ibm.udeploy.install.doc/topics/agent_firewalls.md#).
-   If you are using high-availability, check to see whether there was a failover.
-   If this result happens for only this process, what might be different between this process and the other processes that succeed at running the step?
-   Can the process succeed when the built-in admin ID runs it. When you run the process this way, incorrect permission configuration does not impact process execution.
-   Does this problem happen with any other steps? If not, how is this step different?
-   If you run a process with just this step, does it fail in the same way?

**Process failures occur after an upgrade**

-   Does the new version support the installed Java™ Runtime Environment or Java Development kit?

    **Important:** 

    For best results, download and use the latest available version of the IBM® Java Runtime Environment \(JRE\) for the IBM UrbanCode Deploy server and agent relays. An IBM JRE is available as a separate download. See the [IBM developer kits](https://www.ibm.com/developerworks/java/jdk/) page to get the latest version. Install the IBM JRE according to the documentation on the page. Be sure to set the JAVA\_HOME system variable to the location of the IBM JRE. If you are updating or changing the JRE to the latest version, see [Changing or updating the JRE of servers](../../com.ibm.udeploy.install.doc/topics/../../com.ibm.udeploy.doc/topics/jre_change.md#) and [Updating the JRE location for agent relays](../../com.ibm.udeploy.install.doc/topics/../../com.ibm.udeploy.doc/topics/update_JRE_agent_relays.md#) for instructions. For documentation on the IBM JRE, see [IBM SDK, Java Technology Edition](https://www.ibm.com/support/knowledgecenter/SSYKE2/welcome_javasdk_family.html).

    Using JREs or Java development kits other than those provided by IBM might cause unexpected results.

-   Were there any errors in the upgrade process?
-   Check the agent log file for errors that point to a configuration issue. For example, a port might be blocked or a URL is incorrect. Check the server log file for errors. For example, a port might be blocked or URL is incorrect. See [Viewing logs](log_audit.md#).
-   If you use an agent relay, confirm that the agent relay was upgraded to the same version as the server.
    -   Check the **Agent Relays** tab to verify that the agent relay version is supported. To open the **Agent Relays** tab, click the main **Resources** tab, and then click the **Agent Relays** tab. See the minimum recommended and minimum required versions for the listed agent relays in the upper-right corner of the tab. You might have to upgrade an agent relay or agent relays. For information about upgrading an agent relay, see [Upgrading agent relays](../../com.ibm.udeploy.install.doc/topics/upgrade_agent_relay.md#).
-   Check the **Agents** tab to verify that the server supports the agent version. To open the **Agents** tab, click the main **Resources** tab, and then click the **Agents** tab. See the minimum recommended and minimum required versions for the listed agents in the upper-right corner of the tab. You might have to upgrade an agent or agents. For information about upgrading an agent, see [Upgrading agents](../../com.ibm.udeploy.install.doc/topics/upgradeAgents.md#).
-   Did you create this process in the upgraded version? If the process was created in a previous version, did it work correctly in the previous version? If so, were any changes made to the process after the upgrade?

**A process runs, but it does not stop**

-   Has this process ever run to completion previously? See this IBM support article: [MustGather: How to trace the execution of a process](http://www-01.ibm.com/support/docview.wss?uid=swg21653769).
-   Is the process wired to the **Finish** step?
-   If the step that fails is a shell step, is the standard output is redirected for child processes to https://developer.ibm.com/urbancode/plugindoc/ibmucd/shell/5-562693/usage/?

**Processes fail intermittently**

-   Does the server log contain exceptions that this issue generated?
-   On which step does the process fail? Does the step output contain errors?
-   At which times does the process fail? Check for network outages, maintenance intervals during that time.
-   Is the Download Artifacts step failing with the error `java.io.FileNotFoundException: Artifact set not found`? Ensure that CodeStation has enough time to store the artifacts before they are requested, particularly in high-availability clusters, in which the servers share the artifacts. The solution for this issue is typically to add a Wait step with a few seconds wait time before the Download Artifacts step.

**Processes stop before completion**

-   Check the agent and server log files for errors.
-   Check the process system output.
-   Consider running each process step's equivalent function in a command-line environment to verify that each step works as planned.
-   Can the built-in admin ID run processes with success?
-   If the steps that fail are shell steps, redirect the standard output of child processes to https://developer.ibm.com/urbancode/plugindoc/ibmucd/shell/5-562693/usage/.
-   Do you have sufficient memory on the IBM UrbanCode Deploy server?

    **Tip:** The workflow execution engine that runs the process runs on the IBM UrbanCode Deploy server.

-   On which screen or activity do you see no progress?
-   How long did the process stop? How long do you expect this activity to take?
-   Are there any agents for which this behavior does *not* happen? If so, what differences exist between the processes that work and the processes that do not.
-   Did this behavior always happen? If not, what changed immediately before this problem surfaced?

**Processes with branches do not run correctly**

-   Look closely at the way the process branches to ensure that the process is running in the way as expected. See [Branching and joining steps](comp_process_join.md). See this IBM support article: [MustGather: How to trace the execution of a process](http://www-01.ibm.com/support/docview.wss?uid=swg21653769).

**Processes using impersonation do not run correctly**

-   Reproduce the problem with a simple shell step, use the `#!` syntax at the top to specify the shell to use. For example:

    ```
    #!/bin/sh
    ```

    In the example, `/bin/sh` resolves to different shells depending on the operating system. For example, it resolves to `/bin/ksh` on AIX and Solaris operating systems and to `/bin/bash` on a RedHat Enterprise Linux operating system.

-   Put the shell script of the step into a separate file and execute it from the IBM UrbanCode Deploy interface or from a command line.
-   Enable logging on the agent to verify that the command ran. To enable logging put the following line in the agent-home/conf/agent/log4j.properties file. Start the agent again for the change to take affect.

    ```
     log4j.logger.com.urbancode.shell.impersonation.unix.UnixImpersonateCommand=DEBUG
    ```

-   Add to the separate script file a call to printenv and execute the script from a IBM UrbanCode Deploy step or from a command line. Compare the two processes for differences.
-   Execute the separate script using the commands configured in the **sudoFormat** and **suFormat** agent properties described in the [Impersonation on Linux and UNIX systems](arch_appx_sudo_using.md) topic.
-   In the agent installed.properties file, add the following property to verify that the command executes successfully after the impersonation.

    ```
     com.urbancode.shell.impersonation.unix.scriptPostExecuteAction=echo
    ```

-   Update your Java fixpack level or Java version to a higher level.

**Parent topic:** [Troubleshooting the IBM UrbanCode Deploy server and agents](../topics/trouble_serveragents_ov.md)

