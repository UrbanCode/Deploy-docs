# Reconfiguring agents

You can use the agent configuration script to change agents. For example, you can connect an agent to a new server.

By default, the agent reconfiguration script is in the location agentInstall/bin, where agentInstall is the installation location for the agent. The default installation location is /opt/ucd/agent.

To run the script, go to the agentInstall/bin folder and run the following command:

-   Linux™:

    ```
    ./configure-agent hostname port agentName
    ```

-   Windows™:

    ```
    ./configure-agent.cmd hostname port agentName
    ```


**Important:** You must specify each parameter in this command. If you do not want to change one of the values, you must specify the existing value for the parameter.

-   **`hostname`**

    Specify the host name of the HCL® UrbanCode™ Deploy server that the agent connects to. You can specify a new server or specify the existing server to keep the value unchanged. You cannot change this value on an agent that connects to an agent relay. Also, you cannot change a host name that refers to a server to one that refers to an agent relay.

-   **`port`**

    Specify the server port to connect to. The default value is `7918`. You can specify a new value or specify the existing value to keep the value unchanged.

-   **`agentName`**

    Specify the name for the agent. This name appears in the list of agents on the server. You can specify a new value or specify the existing value to keep the name unchanged.


**Parent topic:** [Installing agents](../../com.ibm.udeploy.install.doc/topics/agent_install_ov.md)

