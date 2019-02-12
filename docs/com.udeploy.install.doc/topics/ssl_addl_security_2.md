# Ensuring end-to-end JMS encryption

All JMS traffic between the JMS agent and the server is encrypted with Transport Layer Security \(TLS\). However, starting with version 6.2.2 of the HCL® UrbanCode™ Deploy, the server creates by default a unique key for JMS agents that connect to it and encrypts all JMS traffic to the agent with this key. This encryption ensures that instructions that are meant for an agent can't be read or used by another client on the JMS mesh.

Upgrade HCL UrbanCode Deploy to version 6.2.2 or later.

1.   Upgrade each agent to version 6.2.2 or later. Agents that are not being upgraded can communicate with the server during this process, so you can upgrade agents one at a time.
2.   Set the system time on the server and the computers that agents are running on to times that are the same or within a few minutes of each other. The server and computers with agents do not have to be in the same time zone, but they must agree about the global time within approximately 5 minutes. 
3.   If it is not feasible to synchronize the system times or if you want to disable end-to-end JMS encryption, add the following line to agent's installed.properties file, and then restart the agent: 

    ```
    agent.jms.disable_full_encryption=true
    ```

4.   In the server configuration file, set the property server.agentCommunicationAlwaysEncrypted to `true`. Now the server accepts connections only from JMS agents that are using a secure connection.

You can view the API key of an agent by clicking **Settings** \> **Security** \> **API Keys and Certificates** on the server. If you suspect that a JMS agent was compromised, select the API key and then click **Actions** \> **Revoke** to revoke the API Key and prevent the agent from connecting to the server.

**Parent topic:** [SSL configuration](../../com.udeploy.doc/topics/SSLinstall.md)

