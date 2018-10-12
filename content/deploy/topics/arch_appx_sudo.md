# User impersonation for process steps {#arch_appx_sudo .concept}

IBM® UrbanCode® Deploy can use user impersonation when an agent must run a command for which it might not otherwise have permission, or when a specific user must be employed for a process.

On UNIX™ and Linux™ systems, the su and sudo commands are used to impersonate users; on Windows™ IBM UrbanCode Deploy provides a utility program to handle impersonation. You implement impersonation when you configure a component's plug-in process step or resource.

-   **[Impersonation on Linux and UNIX systems](../topics/arch_appx_sudo_using.md)**  
The su command \(as used by IBM UrbanCode Deploy\) enables a user to start a shell as another user \(process steps can be considered individual shells\).
-   **[Impersonation on Windows systems](../topics/arch_appx_impersonation_windows.md)**  
For agents that are running on Windows, IBM UrbanCode Deploy provides a program that handles impersonation.
-   **[Impersonation on z/OS systems](../topics/arch_appx_impersonation_zos.md)**  
The su command is used to impersonate users on agent computers that are running IBM z/OS®.

**Parent topic:** [Processes](../topics/comp_workflow.md)

