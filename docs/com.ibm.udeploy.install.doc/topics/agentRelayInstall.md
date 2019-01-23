# Installing agent relays

An agent relay is a communication proxy for agents that are located behind a firewall or in another network location. You can install agent relays in interactive mode or in silent mode.

While there is at least a low-bandwidth WAN connection between the server and remote agents, the HCL® UrbanCode™ Deploy server can send work to agents in other geographic locations through the relay. An agent relay requires that only a single server in the remote network contact the server. Other remote agents communicate with the server by using the agent relay. All agent-server communication from the remote network goes through the relay.

-   **[Installing agent relays in interactive mode](../../com.ibm.udeploy.install.doc/topics/install_agentrelay_interactive.md)**  
Installing an agent relay from the command line involves running a batch file or shell script and specifying information about the agent relay.
-   **[Installing agent relays in silent mode](../../com.ibm.udeploy.install.doc/topics/install_agentrelay_silent.md)**  
In silent mode, you specify the installation properties in a text file and then run the agent relay installation without command-line prompts.

**Parent topic:** [Installing HCL UrbanCode Deploy](../../com.ibm.udeploy.install.doc/topics/install_ch.md)

