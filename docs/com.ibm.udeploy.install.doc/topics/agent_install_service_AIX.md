# Running agents as services on IBM AIX

You can set up agents to run as system services.

Install an agent.

1.   Change the owner of the agent installation folder to the user that runs the agent. For example, if the user `ucdagent` run the agent and the agent installation folder is /opt/ucd/agent, run the following command:

    ```
    chown -R ucdagent /opt/ucd/agent/
    ```

    You can find the user that runs the agent by looking at the USER property on the agent.

2.   Similarly, change the group of the agent installation folder to the group that is associated with the user. For example, if the agent is installed in the folder /opt/ucd/agent, run the following command:

    ```
    chgrp -R ucdagent /opt/ucd/agent/
    ```

3.   Make a copy of the file agent-install/bin/init/agent, where agent-install is the installation folder of the agent. If you are running multiple agents on the system, give the file a unique name, such as ucdagent-A.
4.   In a text editor, edit the file: 

    -   Set the property AGENT\_USER to the name of the user that runs the agent.
    -   Set the property AGENT\_GROUP to the name of the group that is associated with that user.
    -   Set the property SCRIPT to the location of the agent executable file. The default location is /opt/ucd/agent/bin/agent.
    The file might look like the following example:

    ```
    AGENT_HOME="/opt/ucd/agent"
    AGENT_USER="ucdagent"
    AGENT_GROUP="ucdagent"
    
    # == END INSTALL MODIFICATIONS ===================
    
    ANT_HOME="$AGENT_HOME/opt/apache-ant-1.8.4"
    GROOVY_HOME="$AGENT_HOME/opt/groovy-1.8.8"
    SCRIPT="/opt/ucd/agent/bin/agent"
    ```

5.   Configure the agent to run when the system starts. The steps depend on how your IBM® AIX® system manages services. For example, for IBM AIX systems that use `init.d`, follow these steps:

    1.  Copy the file to the folder /etc/rc.d/init.d/.
    2.  Add the file to run level 2. For example, if the file is named ucdagent, run the following command:

        ```
        ln -s /etc/rc.d/init.d/ibm-ucdagent /etc/rc.d/rc2.d/S98ucdagent
        
        
        ```

    For more information on modifying the /etc/inittab file, see [https://www.ibm.com/support/knowledgecenter/en/ssw\_aix\_71/com.ibm.aix.osdevice/modetc.htm](https://www.ibm.com/support/knowledgecenter/en/ssw_aix_71/com.ibm.aix.osdevice/modetc.htm) 


The agent runs as a service. To verify that the agent is running as a service, run the following command and verify that two processes from the agent are running:

```
ps -ef | grep installFolder
```

For `installFolder`, specify the installation folder of the agent, such as /opt/ucd/agent.

For information about the way that IBM AIX handles services, see [Starting and Stopping Software via RC Directories](http://www.ibm.com/support/docview.wss?uid=isg3T1000661).

**Parent topic:** [Installing agents](../../com.ibm.udeploy.install.doc/topics/agent_install_ov.md)

