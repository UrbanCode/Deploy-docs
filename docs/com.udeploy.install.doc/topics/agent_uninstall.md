# Uninstalling agents

To uninstall the agent, stop it, remove its service and registry keys, and delete its files.

You must be an administrator to uninstall an agent.

1.   Change to the directory that hosts the agent. 
2.  Stop the agent.You can stop the agent from the command line or from the server. To stop the agent from the command line, use the following commands:
    -   On Windows™, run this command:

        ```
        agent.cmd stop
        ```

    -   On Linux™ or UNIX™, run this command:

        ```
        ./agent stop
        ```

    -   On z/OS®, cancel the started task for the agent. For example, if the name of the started task is BUZAGNT, run this command:

        ```
        C BUZAGNT
        ```

        If the name of the started task is 8 characters long, specify the address space ID in the cancel command. Cancel the started task and the two spawned tasks. For example, if the name of the started task is UCZAGENT and the address space IDs are 22, 46, and 86, run these commands:

        ```
        C UCZAGENT,A=22
        C UCZAGENT,A=46
        C UCZAGENT,A=86
        ```

3.   If the agent is running as a service on Windows, remove the service and registry keys. 
    1.   Change to the C:\\installed\_agent\\bin\\service folder, where installed\_agent is the location of the agent. 
    2.   Remove the service by running the following command: 

        ```
        _agent.cmd remove service\_name
        ```

        Use the name of the service for `service\_name`. To find the service name, open the services view and find the entry that starts with `HCL® UrbanCode™ Deploy Agent`. The service name is in parentheses in this entry.

4.  Delete the agent installation directory.

**Parent topic:** [Uninstalling HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/uninstall_ch.md)

