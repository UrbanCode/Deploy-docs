# User impersonation for process steps

HCL® UrbanCode™ Deploy can use user impersonation when an agent must run a command for which it might not otherwise have permission, or when a specific user must be employed for a process.

On UNIX™ and Linux™ systems, the su and sudo commands are used to impersonate users; on Windows™ HCL UrbanCode Deploy provides a utility program to handle impersonation. You implement impersonation when you configure a component's plug-in process step or resource.

