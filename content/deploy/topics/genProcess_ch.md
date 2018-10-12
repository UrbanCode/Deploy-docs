# Generic processes {#genprocess_ch .concept}

Generic processes are processes that are designed to run outside normal component or application processing. Generic processes are not specific to a particular component and can be used in any number of applications. They are like general purpose processes. You can use generic processes to download and install packages on the system or perform other configuration management related tasks such as configuring SSH or completing FTP tasks. With a generic process, for example, you can update Linux agents that were recently installed by using SSH to run as a service on a Linux computer. Linux agents cannot be updated in this way during a remote installation.

Generic processes can be used anywhere an application or component process might not be needed. Generic processes are run by agents on hosts that are managed by the agents. You can use generic processes in these instances, for example:

-   In conjunction with a number of different component processes that do not fit well into a component template
-   When you want to run processes that directly affect IBM® UrbanCode® Deploy agents that are unrelated to component, such as changing the agent configuration

Like component processes, generic processes consist of plug-in steps. Generic processes are created in the same way that component processes are created: steps are placed and configured in the process design editor. All plug-ins can be used, but some might be of little or no use outside a deployment. See [Processes](comp_workflow.md).

To run a generic process, click **Processes**, and then click the generic process. On the **Dashboard** tab for the process, specify a resource \(in most cases, an agent\) in the **Resource** list, and then click **Submit**.

Generic processes can also be run from within component processes.

**Tip:** You can set a default resource for generic processes:

1.  Click the generic process to open it.
2.  Open the **Configuration** tab.
3.  Click **Basic Settings**.
4.  In the **Default Resource** field, specify the default resource to run the process on. In most cases, specify an agent.
5.  Click **Save**.

-   **[Importing and exporting generic processes](../topics/genProcess_import.md)**  
You can move generic processes between servers by exporting and importing them.

**Parent topic:** [Processes](../topics/comp_workflow.md)

