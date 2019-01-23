# Removing and reinstalling agents as Windows services

If you installed an agent as a Windows™ service, you can remove and reinstall the service.

Install an agent as a Windows service. See [Installing agents from the command line](../../com.ibm.udeploy.install.doc/topics/agentInstall.md#).

1.   Open a command prompt as an administrator. 
2.   Go to the C:\\agent\_install\\bin\\service folder, where agent\_install is the installed agent location. 
3.   Remove the service by running the following command: 

    ```
    _agent.cmd remove service\_name
    ```

    Use the name of the service for `service\_name`. To find the service name, open the services view and find the entry that starts with `HCL® UrbanCode™ Deploy Agent`. The service name is in parentheses in this entry.

4.   Reinstall the service by running the following command: 

    ```
    _agent.cmd install service\_name
    ```


**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

