# Impersonation on Windows systems {#arch_appx_impersonation_windows .concept}

For agents that are running on Windows™, IBM® UrbanCode® Deploy provides a program that handles impersonation.

You implement impersonation for agents on Windows the same way you do for agents on UNIX™ or Linux™: when you configure a process step, you specify the user credentials that are used when the step is processed. These credentials are the user that the agent is impersonating. In this way, two user accounts are active: the user that the agent runs as normally and the user that the agent is impersonating while it runs the step.

To run steps on Windows, the agent must be running as LocalSystem as a service or running in an administrator command prompt. Also, this user must have the following privileges, at a minimum:

-   SE\_RESTORE\_NAME \(Restore files and directories\)
-   SE\_BACKUP\_NAME \(Back up files and directories\)
-   SE\_INCREASE\_QUOTA\_NAME \(Adjust memory quotas for a process\)
-   SE\_ASSIGNPRIMARYTOKEN\_NAME \(Replace a process-level token\)
-   The user must also have access to the agent working directory.

Also, to impersonate an administrator, the agent user account must have the SE\_TCB\_NAME \(Act as part of the operating system\) permission.

The user that the agent is impersonating must have at least one of the following privileges:

-   SE\_BATCH\_LOGON\_NAME \(Log on as a batch job\)
-   SE\_INTERACTIVE\_LOGON\_NAME \(Log on locally\)
-   SE\_SERVICE\_LOGON\_NAME \(Log on as a service\)

In Windows Vista and later versions of Windows, when the agent logs in as the impersonated user, the operating system returns a restricted token. If the impersonated user is a member of the Administrators group, the agent attempts to get an elevated token. However, if the agent user account does not have the SE\_TCB\_NAME permission, the agent does not receive an elevated token. In this case, the agent attempts to run the step with the restricted token, but it does not have administrator permissions.

You can also impersonate the Windows LocalSystem account. The LocalSystem account is installed on every Windows system and is the equivalent of the root user on UNIX and Linux. It always has the privileges that are listed above.

**Note:** For agents on Windows, the sudo option is ignored if selected.

**Parent topic:** [User impersonation for process steps](../topics/arch_appx_sudo.md)

