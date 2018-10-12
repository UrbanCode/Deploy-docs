# Impersonation on z/OS systems {#arch_appx_impersonation_zos .concept}

The su command is used to impersonate users on agent computers that are running IBM® z/OS®.

The su command starts a shell as a different user. Process steps can be considered individual shells. When you configure a process step, you can specify that the step uses impersonation by selecting the **Use Impersonation** check box. To learn more, see [Processes](comp_workflow.md). On z/OS agent computers, the **Group**, **Password**, and **Use Sudo** fields that are displayed when you click **Use Impersonation** are ignored.

To configure impersonation, supply the user name that is required by the target computer. When the process step that is configured for impersonation runs, the su command runs the step as the impersonated user. You can configure user impersonation independently for each process step. You can also define user impersonation credentials for a resource. To learn more, see [Defining default user impersonation credentials](resources_impersonation.md).

You must configure a Resource Access Control Facility \(RACF®\) profile so that the su command can start a shell as a different user without specifying a password. The following RACF profile grants authority to user X to impersonate user Y without entering a password:

```
RDEFINE SURROGAT BPX.SRV.Y UACC(NONE)
PERMIT BPX.SRV.Y CLASS(SURROGAT) ID(X) ACCESS(READ)
SETROPTS RACLIST(SURROGAT) REFRESH
```

For more information about the su command, see the z/OS UNIX™ Systems Services help.

**Parent topic:** [User impersonation for process steps](../topics/arch_appx_sudo.md)

