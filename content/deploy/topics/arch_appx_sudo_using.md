# Impersonation on Linux and UNIX systems {#arch_appx_sudo_using .concept}

The su command \(as used by IBM® UrbanCode® Deploy\) enables a user to start a shell as another user \(process steps can be considered individual shells\).

When you configure a process step \(see [Processes](comp_workflow.md)\), you can tell IBM UrbanCode Deploy to use impersonation for the step. By default, `su` is used but you can use sudo instead. To configure impersonation, you supply the user name that is required by the target host. When the impersonation-configured process step runs, the su or sudo command runs the step as the impersonated user. Each step that needs user impersonation must be configured independently.

Before `sudo` can be used, impersonation privileges must be defined in the /etc/sudoers file. When you configure sudoers, ensure that the impersonating user does not need to supply a password. Typically, you would configure the /etc/sudoers file like the following example:

```
Defaults:X !requiretty 
```

```
X ALL=(Y) NOPASSWD: ALL 
```

where X and Y are user names. Configured this way, user X can run any command as user Y without supplying a password.

Also, Y can be a comma separated list, as shown here:

```
X ALL=(Y1, Y2, Y3) NOPASSWD: ALL
```

**Note:** The impersonated user must have read and execute access to the agent working directory.

As an alternative to configuring sudoers, in some cases you can configure the PAM via the module `pam_wheel.so` to allow certain users to log in without specifying a password. In this case, add users to a specific `wheel` group and edit the PAM configuration allow users in this group to run commands as though they were the root user.

su and sudo maintain a record in the system logs of all of their activity. su can be used without configuring the sudoers file. For information about su/sudo, see the UNIX™ or Linux™ documentation.

**Note:** For UNIX or Linux agents, the password option is ignored.

To customize the su and sudo commands, you can set the following properties on the agent, in the installed.properties file:

|Property|Default value|Description|
|--------|-------------|-----------|
|com.urbancode.shell.impersonation.unix.sudoFormat|`%s -n -u %u %c`|Syntax of the sudo command|
|com.urbancode.shell.impersonation.unix.sudoGroupFormat|`%s -n -u %u -g %g %c`|Syntax of the sudo command when a group is specified|
|com.urbancode.shell.impersonation.unix.suFormat|`%s - %u -c %c`|Syntax of the su command|

**Tip:** To set these properties on new agents, create a generic process that updates the installed.properties file and run the process on new agents.

1.  Create a generic process that appends the property to the file located at /conf/agent/installed.properties \(for example, use a Shell step to append the property to the file\). Make sure you have the right file, the default working directory for a generic process is \\var\\work. 
2.  Once you've added the property, go to the **Resources -\> Agents** tab, select the agents, and go to **Actions -\> Restart** . This will restart the agent process and pick up the new property. It is recommended restarting no more than ~100 agents at a time to make sure they're all able to reconnect to the server quickly. \(If the agents are installed as services and you don't mind restarting the whole machine, you could alternatively use the Linux or Windows System tools plug-ins to restart the whole machine as part of the generic process, removing the need to restart all the agents from the UI.\)
3.  If later you need to run the generic process in bulk, you can create an application just for that purpose and add all the agents to an environment. You can then use the **For every agent** step to run a generic process on all the agents at once. It is recommended you should only do this process on a few agents so that you can test that everything is configured properly before moving to configuring the agents in bulk.

You can use the following variables in these properties:

|Variable|Value|
|--------|-----|
|`%s`|The location of the su or sudo executable|
|`%u`|The user|
|`%g`|The group|
|`%c`|The command to run|

**Parent topic:** [User impersonation for process steps](../topics/arch_appx_sudo.md)

