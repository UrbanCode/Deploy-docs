# Upgrading encryption key strength

When you upgrade the server from version 6.0.1.1 or earlier to a version later than version 6.0.1.1, you can upgrade the SSL encryption.

This upgrade is optional, but it strengthens server security. The keytool application is included in the Java™ developer kit and is not part of HCL® UrbanCode™ Deploy.

1.  Upgrade the HTTPS certificate for the server: 
    1.  On the server, open a command-line window to the server\_install/opt/tomcat/conf folder, where server\_install is the server installation folder.The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™. 
    2.  Delete the existing certificate with the following command: 

        ```
        keytool -delete 
          -alias tomcat 
          -keystore tomcat.keystore 
          -storepass changeit
        ```

        **Note:** Each command in this example must be written on one line. Also, the commands in the following examples must be written on one line. The commands are written on multiple lines for clarity.

    3.  Create a certificate with the following command: 

        ```
        keytool -genkey 
          -alias tomcat 
          -storepass changeit 
          -keypass changeit 
          -keyalg RSA 
          -sigalg SHA256withRSA 
          -keysize 2048 
          -validity 7305 
          -dname CN=host\_name 
          -keystore tomcat.keystore
        ```

        For `host\_name`, use the host name of the server.

    4.   Go to the folder app\_data/conf. 
    5.  Delete the existing entry to the keystore with the following command:

        ```
        keytool -delete 
          -alias server 
          -keystore server.keystore 
          -storepass changeit
        ```

    6.  Create an entry to the keystore with the following command: 

        ```
        keytool -genkey 
          -alias server 
          -storepass changeit 
          -keypass changeit 
          -keyalg RSA 
          -sigalg SHA256withRSA 
          -keysize 2048 
          -validity 7305 
          -dname CN=host\_name 
        -keystore server.keystore
        ```

        For `host\_name`, use the host name of the server.

2.  For each of your agent relays, upgrade the encryption with the following steps: 
    1.  In a command-line window, go to the relay\_install/conf/jms-relay folder, where relay\_install is the relay installation folder. 
    2.  Delete the existing entry in the keystore for the agent relay with the following command:

        ```
        keytool -delete 
          -alias agentrelay 
          -keystore agentrelay.keystore 
          -storepass changeit
        ```

    3.  Add an entry with the new encryption level with the following command:

        ```
        keytool -genkey 
          -alias agentrelay 
          -keystore agentrelay.keystore 
          -storepass changeit 
          -keypass changeit 
          -keyalg RSA 
          -sigalg SHA256withRSA 
          -keysize 2048 
          -validity 7305 
          -dname CN=host\_name
        ```

        For `host\_name`, use the host name of the server.

3.  If you are using mutual encryption between servers and agents, upgrade the encryption on each agent: 
    1.  In a command-line window, go to the agent\_install/conf/jms-relay folder, where agent\_install is the agent installation folder. 
    2.  Delete the existing entry in the keystore for the agent with the following command:

        ```
        keytool -delete 
          -alias alias 
          -keystore keystore\_file 
          -storepass changeit
        ```

        Replace the alias variable with the alias of the server certificate in the agent keystore. The keystore\_file variable represents the keystore file. The default name of the keystore file is agent.keystore. To find the alias, run the following command, and look for the alias name in the output:

        ```
        keytool -list -v -keystore keystore\_file
        ```

    3.  Follow the steps in [Configuring mutual authentication](ssl_mutual_auth.md) to add the new server certificate to the agent. 

**Parent topic:** [Upgrading and migrating](../../com.ibm.udeploy.doc/topics/c_node_upgrading.md)

