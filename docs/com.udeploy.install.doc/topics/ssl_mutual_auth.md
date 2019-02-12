# Configuring mutual authentication

To use mutual authentication, servers and Java Message Service \(JMS\) agents must exchange keys. You export a server key as a certificate and import it into the JMS agent keystore. Then, you reverse the process by exporting the agent key and importing it into the server keystore.

Before you exchange keys, ensure that the following properties are set:

1.  Set the server.jms.mutualAuth property in the server's installed.properties file \(in the server\_install/conf/server directory\) to `true`.
2.  For each JMS agent, set the locked/agent.mutual\_auth property in the agent's installed.properties file \(in the agent\_install\\conf\\agent directory\) to `true`.
3.  For each agent relay, set the agentrelay.jms\_proxy.secure property in the relay's agentrelay.properties file \(in the relay\_install\\conf directory\) to `true`.
4.  For each agent relay, set the agentrelay.jms\_proxy.mutualAuth property in the relay's agentrelay.properties file to `true`.

Additionally, ensure that the keytool utility, which is provided with the Java™ developer kit and is not part of HCL® UrbanCode™ Deploy, is available in the system path on each server, agent, and agent relay.

Each server, JMS agent, and agent relay contains a key that identifies that component. By default, these keys are stored in self-signed certificates that are created automatically during product initial startup. You can replace these self-signed certificates with either signed certificates that you obtain from a well-known certificate authority \(CA\), or you can issue certificates using an internal CA.

-   If you enable mutual authentication and use self-signed certificates, you must exchange the keys between server and agent relay, agent relay and agent, or between server and agent.
-   If you use mutual authentication and certificates signed by an internal CA, you must ensure that the root certificates of the certificate chains are trusted by the Java virtual machine of the receiver. You do not have to exchange individual keys.
-   If you use mutual authentication and certificates signed that are by a well-known CA that is trusted by the Java virtual machine, you do not have to exchange keys or root certificates.

The advantage of using any form of signed certificates for mutual authentication is that you do not have to restart the server or agent relay every time you add the key for a new agent to the server or relay keystore. Any agent that supplies a certificate that is trusted by the server or agent relay that it connects to is allowed to communicate with the server or agent relay.

The keys for mutual authentication are stored in the following keystore files.

-   server.keystore in the conf folder of each server
-   agent.keystore in the conf folder of each JMS agen
-   agentrelay.keystore in the conf/jms-relay folder of each agent relay

**Note:** agent.keystore contains two self-signed certificates with the following aliases.

-   ibm-ucd\_agent \(for JMS mutual authentication in JMS agents\)
-   ucd-agent-<id\> \(for end-to-end JMS encryption in JMS agents and for the web protocol in web agents\)

In the following steps, you export the key from each system and import it into each component by using the keytool utility.

To configure mutual authentication for high-availability environments, swap all JMS agents, or agent relay, certificates with each server. Ensure that all JMS agents and agent relays have certificates from all servers, and all servers have certificates from all JMS agents and agent relays. Importantly, ensure that each server uses the same certificate. For this purpose, load balancers can be ignored.

1.   Copy the certificate from the server to each JMS agent or agent relay that connects directly to the server: 
    1.   On the server, open a command-line window and go to the folder that contains the server.keystore file. By default, this folder is located in the app\_data/conf folder, where app\_data is the application data folder that you set during installation. The default application data folders are as following, depending on the operating system:

        -   Linux: /opt/ucd/server/appdata
        -   Windows: C:\\Program Files\\ucd\\server\\appdata
        In the case of a high-availability cluster, the application data folder is usually on a shared remote directory.

    2.   Run the following command to export the server key. 

        ```
        keytool -exportcert -keystore server.keystore -storepass changeit -alias server -file server.crt
        ```

        If the certificate was exported, you see this message: `Certificate stored in file server.crt`.

    3.   Copy the exported server.crt key file to each JMS agent installation conf directory or the agent relay installation conf/jms-relay directory. 
    4.   Import the server certificate into the JMS agent or agent relay keystore with the following command from within the agent's conf directory or the agent relay's jms-relay directory: 

        ```
        keytool -importcert -keystore keystoreFile -storepass changeit -alias server -file server.crt -keypass changeit -noprompt
        ```

        For keystoreFile, use agent.keystore for JMS agents and agentrelay.keystore for agent relays. If the certificate was imported, you see this message: `Certificate was added to keystore`. The agent.keystore and encryption.keystore files are not generated until the first time that the JMS agent runs.

    5.   Repeat the process for each JMS agent and agent relay that connects directly to the server. 

        **Note:** JMS agents that communicate with the server through agent relays do not have to swap certificates with the server. Only the agent relay that connects to the server must swap certificates with the server. However, you must swap certificates between the agent relay and each remote JMS agent.

2.   Copy the certificate from each JMS agent or agent relay that connects directly to the server and import that certificate into the server keystore: 
    1.   On the system that hosts the JMS agent or agent relay, open a command-line window and go to the folder that contains the agent.keystore or agentrelay.keystore file. 
    2.   run this command to export the certificate. 

        ```
        keytool -exportcert -keystore keystoreFile -storepass changeit 
        -alias ibm-ucd_agent -file agentName.crt
        ```

        For keystoreFile, use agent.keystore for JMS agents and agentrelay.keystore for agent relays. The default JMS agent alias is `ibm-ucd_agent`. For agentName, specify a unique string identifier for the agent or agent relay. If the certificate was exported, you see this message: `Certificate stored in file agentName.crt`.

    3.   Copy the exported key file to the server app\_data/conf folder, where app\_data is the application data folder. 
    4.   Import the JMS agent or agent relay certificate into the server keystore with the following command: 

        ```
        keytool -importcert -keystore server.keystore -storepass changeit 
        -alias uniqueAlias -file agentName.crt -keypass changeit -noprompt
        ```

        For uniqueAlias, use a unique key alias that identifies the JMS agent. If the certificate was imported, you see this message: `Certificate was added to keystore`. The agent.keystore and encryption.keystore files are not generated until the first time that the JMS agent runs.

    5.   Repeat the process for each JMS agent and agent relay that connects directly to the server. 

        **Note:** JMS agents that communicate with the server through agent relays do not have to swap certificates with the server. Only the agent relay that connects to the server must swap certificates with the server. However, you must swap certificates between the agent relay and each remote JMS agent.

3.   For each local JMS agent or agent relay, set the key alias to the same value that you used on the server. From the JMS agent's conf directory or the agent relay's jms-relay directory, run this command:

    ```
    keytool -changealias -destalias uniqueAlias -alias defaultAlias -keystore agent.keystore -storepass changeit
    ```

    The default JMS agent alias is `ibm-ucd_agent`, and the default agent relay alias is `agentrelay`.

4.   If you use agent relays, use the established methods to connect remote JMS agents to them. Each remote JMS agent must import the certificate for the relay, and the relay must import the certificate from each remote JMS agent in addition to the certificate from the server.
5.   Restart the server, JMS agents, and agent relays. 

Ensure that the JMS agents and agent relays can connect to the server.

You can also list the certificates that are loaded into a keystore by running the following command from within the conf directory:

```
keytool -list -keystore keystoreFile -storepass changeit
```

**Parent topic:** [SSL configuration](../../com.udeploy.doc/topics/SSLinstall.md)

