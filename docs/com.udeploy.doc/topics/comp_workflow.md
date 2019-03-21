# Processes

Processes are automated tasks that run on agents.

There are three types of processes:

-   Generic processes run outside the context of components or applications. Generic processes are shown on the top-level **Processes** tab. You can use generic processes in these instances, for example:
    -   In conjunction with a number of different component processes that do not fit well into a component template
    -   When you want to run processes that directly affect HCL® UrbanCode™ Deploy agents that are unrelated to component, such as changing the agent configuration
-   Application processes run within the context of applications. In many cases, application processes call component processes. For example, an application process can call the component processes that deploy their associated components.
-   Component processes run tasks on a single component, such as deploying it, uninstalling it, or running configuration tasks on it.

Processes are lists of steps and connections between those steps. Each step is an individual command that runs on a target computer. Steps can manipulate files, run system commands, download files, and run programs. Plug-ins contribute most of these steps; plug-ins are available that work with many different types of software. For information about steps that are provided by plug-ins, see the documentation for the individual plug-in on IBM® developerWorks®: [IBM UrbanCode™ Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

You use the process editor to work with processes. See [Editing processes](comp_workflow_edit.md).

Each time you request a process, the server keeps a log of information about the process and the individual logs from each step. To download these logs, open the process request and click **Download All Logs**.

