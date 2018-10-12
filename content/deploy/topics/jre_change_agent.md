# Changing or updating the JRE of agents {#jre_change_agent .task}

You can change the JRE of active agents by editing their configuration files.

The new JRE must be from the same vendor as the current JRE.

1.   Install the new JRE. 
2.   On the agent system, stop the agent. Do not use the server UI to stop the agent.
3.   If the agent is installed on Linux™, update the location of the JRE in the following places. 

    **Note:** As a shortcut, you can delete the old JRE and move the new JRE into the location of the old JRE. In this case, you do not need to update the properties in the following files because they now point to the new JRE.

    1.   In the file installation\_directory/bin/configure-agent, set the value of the JAVA\_HOME property to the location of the JRE. 
    2.   In the file installation\_directory/bin/agent, set the value of the JAVA\_HOME property to the location of the JRE. 
    3.   In the file installation\_directory/conf/agent/installed.properties, set the value of the IBM\\ UrbanCode\\ Deploy/java.home property to the location of the JRE. If the JRE is in /opt/ibm/java-x86\_64-71/jre, use the following code: `IBM\ UrbanCode\ Deploy/java.home=/opt/ibm/java-x86_64-71/jre` 
4.   If the agent is installed on Windows™, update the location of the JRE in the following places. 

    **Note:** As a shortcut, you can move the new JRE into the location of the old JRE. In this case, you do not need to update the properties in the following files because they now point to the new JRE.

    1.   In the file installation\_directory\\bin\\configure-agent.cmd, set the value of the JAVA\_HOME property to the location of the JRE. 
    2.   In the file installation\_directory\\conf\\agent\\installed.properties, set the value of the IBM\\ UrbanCode\\ Deploy/java.home property to the location of the JRE. For example, if the JRE is in C:\\Program Files\\IBM\\Java71\\jre, use the following code: `IBM\ UrbanCode\ Deploy/java.home=C\:\\Program Files\\IBM\\Java71\\jre` 
5.   If the agent is running as a service on Windows, remove and reinstall the service See [Removing and reinstalling agents as Windows services](agent_service_windows.md#).
6.   On the agent system, start the agent. Do not use the server UI to restart the agent because in this case the JRE is not updated.

**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

