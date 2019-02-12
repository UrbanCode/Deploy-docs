# Changing passwords for the agent relay keystores

You can change the Java™ keystore passwords for the agent relay.

Each agent relay contains two keystores. The agentrelay keystore controls the JMS connection between the agent relay and the server and agents. The codestation keystore controls HTTPS connections to the agent relay and is used with server identity verification. See [Enabling server identity verification](../../com.udeploy.install.doc/topics/ssl_addl_security.md#).

By default, the password for each agent relay Java keystore must be identical to its certificate password. After you change both a keystore password and the corresponding certificate password, you must update the password in the agent relay properties.

Changing the passwords requires the keytool application, which is included in the Java developer kit and is not part of HCL® UrbanCode™ Deploy.

1.  Stop the agent relay.
2.   Change the agentrelay keystore password for the agent relay. 
    1.   Open a command-line window, and go to the /agent-relay-install/conf/jms-relay directory. By default, the agent-relay-install location is `/opt/ibm/agentrelay` on Linux™ and `C:\Program Files\IBM\agentrelay` on Windows™. 
    2.   Change the agentrelay keystore password by using this command: 

        ```
        keytool -storepasswd -new newpassword -keystore agentrelay.keystore
        -storepass changeit
        ```

        The default password for this keystore is changeit.

    3.   Change the agentrelay certificate by using this command: 

        ```
        keytool -keypasswd -alias agentrelay -keypass changeit -new newpassword -keystore agentrelay.keystore -storepass newpassword
        ```

        The default keystore alias is agentrelay, and its value is shown in the `agentrelay.cert.alias` property in the agent-relay-install/conf/agentrelay.properties file.

    4.   In a text editor, open the agent-relay-install/conf/agentrelay.properties file. 
    5.   Specify the new Java keystore password for the agent relay in the following line of code: 

        ```
        agentrelay.keystore.password=newPassword
        ```

        **Note:** For best results, make the Java keystore password and certificate password identical. If the passwords cannot be identical, add the `agentrelay.cert.password=certpassword` property to a new line in the agent-relay-install/conf/agentrelay.properties file.

3.   Change the codestation keystore password for the agent relay. 
    1.   Open a command-line window, and go to the /agent-relay-install/conf directory. By default, the agent-relay-install location is `/opt/ibm/agentrelay` on Linux and `C:\Program Files\IBM\agentrelay` on Windows. 
    2.   Change the codestation keystore password by using this command: 

        ```
        keytool -storepasswd -new newpassword -keystore codestation.keystore
        -storepass changeit
        ```

        The default password for this keystore is changeit.

    3.   Change the codestation certificate password by using this command: 

        ```
        keytool -keypasswd -alias agentrelay -keypass changeit -new newpassword -keystore codestation.keystore -storepass newpassword
        ```

        The default keystore alias is agentrelay, and its value is shown in the `codestation.cert.alias` property in the agent-relay-install/conf/agentrelay.properties file.

    4.   In a text editor, open the agent-relay-install/conf/agentrelay.properties file. 
    5.   Specify the new Java keystore password for the agent relay in the following line of code: 

        ```
        codestation.keystore.password=newPassword
        ```

4.  Start the agent relay.

The agent relay keystore passwords are changed and are obfuscated in the agent-relay-installconf\\server\\agentrelay.properties file.

**Parent topic:** [Agents and agent relay configuration](../topics/configure_agents.md)

