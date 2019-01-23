# Configuring mutual authentication

To use mutual authentication, servers and JMS agents must exchange keys. You export a server key as a certificate and import it into the JMS agent keystore. Then, you reverse the process by exporting the agent key and importing it into the server keystore.

Before you exchange keys, ensure that the following properties are set:

1.  The server.jms.mutualAuth property in the server's installed.properties file \(in the server\_install/conf/server directory\) is set to `true`.
2.  For each JMS agent, the locked/agent.mutual\_auth property in the agent's installed.properties file \(in the agent\_install\\conf\\agent directory\) is set to `true`.
3.  For each agent relay, the agentrelay.jms\_proxy.secure property in the relay's agentrelay.properties file \(in the relay\_install\\conf directory\) is set to `true`.
4.  For each agent relay, the agentrelay.jms\_proxy.mutualAuth property in the relay's agentrelay.properties file is set to `true`.

Additionally, ensure that the keytool utility, which is provided with the Java™ developer kit and is not part of HCL® UrbanCode™ Deploy, is available in the system path on each server, agent, and agent relay.

Each server, JMS agent, and agent relay contains a key that identifies that system. Mutual authentication ensures the identity of each of those systems by exchanging these keys with each other. The keys are stored in the file encryption.keystore in the conf folder of each server, JMS agent, and agent relay. In the following steps, you export the key from each system and import it into each other system using the keytool utility.

To configure mutual authentication for high-availability environments, swap all JMS agent, or agent relay, certificates with each server. Ensure that all JMS agents and agent relays have certificates from all servers, and all servers have certificates from all JMS agents and agent relays. Importantly, ensure that each server uses the same certificate. For this purpose, load balancers can be ignored.

**Note:** Mutual authentication is not used with Web agents.

1.   Copy the certificate from the server to each JMS agent or agent relay that connects directly to the server: 
    1.   On the server, open a command-line window and go to the folder that contains the file server.keystore. By default, this folder is at the location app\_data/conf, where app\_data is the application data folder that you set at installation. The default application data folder is /opt/ucd/server/appdata on Linux™ and C:\\Program Files\\ucd\\server\\appdata on Windows™. In the case of a high-availability cluster, the application data folder is usually on a shared remote directory.
    2.   Export the server key by running the following command: 

        ```
        keytool -exportcert -keystore server.keystore -storepass changeit -alias server -file server.crt
        ```

        If the certificate was exported, you see this message: `Certificate stored in file server.crt`.

    3.   Copy the exported key file server.crt to each JMS agent installation conf directory or the agent relay installation conf/jms-relay directory. 
    4.   Import the server certificate into the JMS agent or agent relay keystore by running the following command from within the agent's conf directory or the agent relay's jms-relay directory: 

        ```
        keytool -importcert -keystore keystoreFile -storepass changeit -alias server -file server.crt -keypass changeit -noprompt
        ```

        For keystoreFile, use agent.keystore for JMS agents and agentrelay.keystore for agent relays. If the certificate was imported, you see this message: `Certificate was added to keystore`. The agent.keystore and encryption.keystore files are not generated until the first time the JMS agent is run.

    5.   Repeat the process for each JMS agent and agent relay that connects directly to the server. 

        **Note:** JMS agents that communicate with the server through agent relays do not have to swap certificates with the server. Only the agent relay that connects to the server must swap certificates with the server. However, you must swap certificates between the agent relay and each remote JMS agent.

2.   Copy the certificate from each JMS agent or agent relay that connects directly to the server and import that certificate into the server keystore: 
    1.   On the system that hosts the JMS agent or agent relay, open a command-line window and go to the folder that contains the file agent.keystore or agentrelay.keystore. 
    2.   Export the certificate by running the following command: 

        ```
        keytool -exportcert -keystore keystoreFile -storepass changeit 
        -alias ucd_agent -file agentName.crt
        ```

        For keystoreFile, use agent.keystore for JMS agents and agentrelay.keystore for agent relays. The default JMS agent alias is `ucd_agent`. For agentName, specify a unique string identifier for the agent or agent relay. If the certificate was exported, you see this message: `Certificate stored in file agentName.crt`.

    3.   Copy the exported key file to the server app\_data/conf folder, where app\_data is the application data folder. 
    4.   Import the JMS agent or agent relay certificate into the server keystore by running the following command: 

        ```
        keytool -importcert -keystore server.keystore -storepass changeit 
        -alias uniqueAlias -file agentName.crt -keypass changeit -noprompt
        ```

        For uniqueAlias, use a unique key alias that identifies the JMS agent. If the certificate was imported, you see this message: `Certificate was added to keystore`. The agent.keystore and encryption.keystore files are not generated until the first time the JMS agent is run.

    5.   Repeat the process for each JMS agent and agent relay that connects directly to the server. 

        **Note:** JMS agents that communicate with the server through agent relays do not have to swap certificates with the server. Only the agent relay that connects to the server must swap certificates with the server. However, you must swap certificates between the agent relay and each remote JMS agent.

3.   For each local JMS agent or agent relay, set the key alias to the same value that you used on the server. From the JMS agent's conf directory or the agent relay's jms-relay directory, run the following command:

    ```
    keytool -changealias -destalias uniqueAlias -alias defaultAlias -keystore agent.keystore -storepass changeit
    ```

    The default JMS agent alias is `ucd_agent`, and the default agent relay alias is `agentrelay`.

4.   If you use agent relays, use the established methods to connect remote JMS agents to them. Each remote JMS agent must import the certificate for the relay, and the relay must import the certificate from each remote JMS agent in addition to the certificate from the server.
5.   Restart the server, JMS agents, and agent relays. 

Ensure that the JMS agents and agent relays can connect to the server.

You can also list the certificates that are loaded into a keystore by running the following command from within the conf directory:

```
keytool -list -keystore keystoreFile -storepass changeit
```

For more information about exchanging keys among servers, see [Sharing secured properties among servers](ssl_mutual_authServers.md#).

To revoke the keys that the JMS agent uses to connect to the server, follow these steps:

1.  Log in as a user with the "Manage Security" permission.
2.  Open the JMS agent and then click **Configuration** \> **Agent Security**. This tab is only shown if you have the "Manage Security" permission and if the JMS agent uses mutual authentication to connect to the server.
3.  To revoke the API key that the JMS agent uses, click **Forget API Key**. Clicking this button is equivalent to removing the API key on the **Settings** \> **API Keys and Certificates** \> **API Keys** and removing the key there.
4.  To revoke the JMS certificate that the agent uses to connect to the server, click **Revoke API Key**.

**Parent topic:** [SSL configuration](../../com.ibm.udeploy.doc/topics/SSLinstall.md)

