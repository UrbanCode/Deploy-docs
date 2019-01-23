# Changing passwords for the server KeyStore

You can change the Java™ KeyStore password for the server.

The server Java KeyStore password must be identical to its certificate password. After you change both the server KeyStore password and certificate password, you must update the password in the server properties.

1.   Stop the server. 
2.   Open a command-line window, and go to the appdata/conf directory. 
3.   Change the server KeyStore password by using this command: 

    ```
    keytool -storepasswd -new newStorePassword -keystore server.keystore
    -storepass changeit
    ```

    The default server password is changeit. The keytool application is included in the Java developer kit and is not part of HCL® UrbanCode™ Deploy.

4.   Change the certificate password by using this command: 

    ```
    keytool -keypasswd -alias server -keypass changeit -new newKeyPassword -keystore server.keystore -storepass newStorePassword
    ```

    The default server alias is server.

5.   In a text editor, open the server-install\\conf\\server\\secured-installed.properties file. 
6.   Specify the new Java KeyStore password for the server in the following line of code: 

    ```
    server.keystore.password=newStorePassword
    ```

    The `javax.net.ssl.trustStorePassword` property takes precedence over the `secured-server.keystore.password` property. If it is present in server-install\\conf\\server\\secured-installed.properties file, update its password with this code: `javax.net.ssl.trustStorePassword=newpassword`. This property applies to all relevant KeyStores.

7.  Specify the new Certificate password for the server in the following line of code: 

    ```
    server.key.password=newKeyPassword
    ```

8.   Start the server. 

The server KeyStore password is changed and is obfuscated in the server-install/conf/server/secured-installed.properties file.

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

