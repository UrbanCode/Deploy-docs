# Managing agents remotely

After an agent is installed, you can manage \(with the monitor process\) many of its features from the HCL® UrbanCode™ Deploy web application.

We characterize an agent as a single process, but technically an agent consists of two processes: a worker process and a monitor process. Worker processes do the actual work of deployment, such as handling plug-in steps. Monitor processes manage the worker process, such as handling restarts, upgrades, and tests. Agent properties can be changed directly by editing the agent's conf/agent/installed.properties file and restarting the agent.

1.   Display the Agents pane \(**Resources** \> **Agents**\). 
2.  Click an action link for the agent.Actions are described in the following table.

    |Action|Description|
    |------|-----------|
    |Edit|This option edits the agent's description.|
    |Restart|This option shuts down and restarts the agent. While the agent is shut down, its status is `Offline`.|
    |Upgrade|This option shuts down the agent and applies the upgrade. While the agent is shut down, its status is `Offline`. After the upgrade is applied, the agent is restarted.|
    |Test|This option runs an agent settings and connection test. Test results are displayed in the Connection Test dialog.|
    |Delete|Removes the agent.|


**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

