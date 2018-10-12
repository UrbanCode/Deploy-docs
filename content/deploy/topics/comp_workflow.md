# Processes {#comp_workflow .concept}

Processes are automated tasks that run on agents.

There are three types of processes:

-   Generic processes run outside the context of components or applications. Generic processes are shown on the top-level **Processes** tab. You can use generic processes in these instances, for example:
    -   In conjunction with a number of different component processes that do not fit well into a component template
    -   When you want to run processes that directly affect IBM® UrbanCode® Deploy agents that are unrelated to component, such as changing the agent configuration
-   Application processes run within the context of applications. In many cases, application processes call component processes. For example, an application process can call the component processes that deploy their associated components.
-   Component processes run tasks on a single component, such as deploying it, uninstalling it, or running configuration tasks on it.

Processes are lists of steps and connections between those steps. Each step is an individual command that runs on a target computer. Steps can manipulate files, run system commands, download files, and run programs. Plug-ins contribute most of these steps; plug-ins are available that work with many different types of software. For information about steps that are provided by plug-ins, see the documentation for the individual plug-in on IBM developerWorks®: [IBM UrbanCode™ Deploy Plug-ins](https://developer.ibm.com/urbancode/plugins/ibm-urbancode-deploy).

You use the process editor to work with processes. See [Editing processes](comp_workflow_edit.md).

Each time you request a process, the server keeps a log of information about the process and the individual logs from each step. To download these logs, open the process request and click **Download All Logs**.

-   **[Process step types and logic](../topics/process_steps.md)**  
When you design processes, you use different kinds of process steps and joining techniques. You can assign properties to process steps and use them to control step execution.
-   **[Component processes](../topics/intro_component_processes.md)**  
A component process is a series of user-defined steps that operate on a component's artifacts. Each component has at least one process that is defined for it and can have several.
-   **[Application processes](../topics/app_process.md)**  
You can use application processes to deploy or to roll back components.
-   **[Generic processes](../topics/genProcess_ch.md)**  
Generic processes are not specific to a particular component and can be used in any number of applications. They are like general purpose processes. You can use generic processes to download and install packages on the system or perform other configuration management related tasks such as configuring SSH or completing FTP tasks. With a generic process, for example, you can update Linux agents that were recently installed by using SSH to run as a service on a Linux computer. Linux agents cannot be updated in this way during a remote installation.
-   **[Editing processes](../topics/comp_workflow_edit.md)**  
In the process editor you organize the steps in a process, specify their properties, and connect them to each other.
-   **[Working on processes in safe edit mode](../topics/process_drafts.md)**  
Safe editing enables you to test component processes before making them available in normal environments. Make updates to your component process, test those updates safely, and then promote to a new version when you are ready.
-   **[Running processes](../topics/comp_workflow_running.md)**  
The way you run a process is different for each type of process.
-   **[Adding process properties](../topics/comp_workflow_property.md)**  
A process property provides a way to add user-supplied information to a process. A running process can prompt users for information and then incorporate it into the process. For example, if the process entails authenticating with another server, you can require that a user enter an ID and a password for the process to continue. Properties are defined in the Edit Property dialog box.
-   **[Copying process steps](../topics/comp_workflow_copy.md)**  
You can copy and paste process steps in all process types: component, application, approval, and generic.
-   **[Manage process step authentication](../topics/process_token_restrict.md)**  
Use token restrictions to manage process step authentication.
-   **[User impersonation for process steps](../topics/arch_appx_sudo.md)**  
IBM UrbanCode Deploy can use user impersonation when an agent must run a command for which it might not otherwise have permission, or when a specific user must be employed for a process.
-   **[Process steps: Reference](../topics/app_processSteps.md)**  
Application processes, component processes, and generic processes are created with the process editor.

**Parent topic:** [Modeling software deployment](../topics/part_using.md)

