# Updating the JRE location for agent relays {#update_JRE_agent_relays .task}

If you upgrade the JRE and change the JRE location, you must also update the agent relays. If you do not change the location of the JRE, you do not have to update these files.

**Important:** Beginning in version 6.2.2, the IBM® UrbanCode® Deploy server and agent relays require a Java™ Runtime Environment \(JRE\) or Java™ Development Kit \(JDK\) version 8.

If you are upgrading from a version prior to 6.2 to version 6.2 or later, and the server is using an IBM JRE, be sure that you upgraded the JRE to the version that came with your current version of IBM UrbanCode Deploy.

1.   Stop the agent relay. 
2.   In the installation folder, locate and open this file for editing: install dir/bin/agentrelay.cmd \(Windows\) or install dir/bin/agentrelay \(Linux\). 
3.   In the file, edit the line that begins `set JAVA_HOME=` to point to your JRE. For example, `set JAVA_HOME=C:\\Program Files\\Java\\jre8` \(Windows\) or `set JAVA_HOME=/opt/java/jre8` \(Linux\).
4.   If you are running agent relays as a Windows™ service, follow these steps: 
    1.   Locate and open this file for editing: install dir/services/agentrelay.cmd. 
    2.   In the agentrelay.cmd file, edit the line that begins `set JAVA_HOME=` to point to your JRE. For example, `set JAVA_HOME=C:\\Program Files\\Java\\jre8`.
5.   Start the agent relay. 

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

