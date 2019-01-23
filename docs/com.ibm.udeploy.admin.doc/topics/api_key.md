# Checking and resetting the API key and certificate for agents

You can view the API key of an agent and reset the key.

API keys can allow agents to access to the HCL® UrbanCode™ Deploy server. Without the correct API key, the server and an agent cannot exchange messages. The server rejects messages that purport to be from the agent if the messages are not encrypted with the key. Likewise, the agent rejects messages that purport to be from the server if the messages are not encrypted with the key. Finally, without the key, no one can read intercepted messages between the server and agent.

The server generates the API key when an agent first requests one. Then, the identity of the agent is recorded as a certificate that the agent provides, and only that identity can request that a new key be generated to replace the existing key. If a key is lost, for example if an agent is reinstalled or compromised, retrieving or generating the exact again is not supported. You must revoke the old key and generate a new one.

1.  Follow these steps to view and regenerate the key of an agent:
2.   On the server, **Settings**, and then under Security, click **API Keys And Certificates**. The API Keys window opens. This window shows the API keys that agents are using to connect to the server.
3.   On the API Keys window, revoke the API key for the agent by selecting the key and clicking **Actions** \> **Revoke**. To find the key that is associated with an agent, open the agent properties and find the property sys.locked/agent.id. The agent API key begins with `ucd-agent-` and the value of the sys.locked/agent.id property.
4.   On the system that hosts the agent, delete the file conf/agent/agent-key.properties. 
5.   Restart the agent. 
6.   Verify that the agent can connect to the server. 

**Parent topic:** [Managing security](../../com.ibm.udeploy.admin.doc/topics/security_ch.md)

