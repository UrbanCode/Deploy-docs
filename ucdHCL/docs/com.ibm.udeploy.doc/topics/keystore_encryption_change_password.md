# Changing passwords for the encryption KeyStore

You can change passwords for the encryption KeyStore.

The encryption.keystore password must be identical to the certificate password.

1.   Stop the server. 
2.   Open a command line window, and go to the app\_data/conf directory. 
3.   To view the alias of the secret key, run the following command: 

    ```
    keytool -keystore encryption.keystore -list -storetype jceks -storepass changeit
    ```

    Make a note of the alias of secret key, it is required in step [6](#a). The keytool application is included in the Java™ developer kit and is not part of HCL® UrbanCode™ Deploy.

4.   Back up the encryption.keystore file. 
5.   Change the encryption KeyStore password by using the following command: 

    ```
    keytool -storepasswd -new newPassword -keystore encryption.keystore -storetype jceks -storepass changeit
    ```

    The default password is changeit. Replace `newPassword` with your password of choice. The keytool application is included in the Java developer kit and is not part of HCL UrbanCode Deploy.

6.   Change the secret key password by using the following command: 

    ```
     keytool -keypasswd -alias XXX -keypass changeit -new newpassword -keystore encryption.keystore -storetype jceks -storepass newpassword
    ```

    where `alias` is the one that you noted in step [3](#b), and the encryption KeyStore password and the secret key password must be the same.

7.   In a text editor, open the server-install\\conf\\server\\secured-installed.properties file. Specify the new encryption.keystore password in the following line of code: 

    ```
     encryption.keystore.password=newPassword
    ```

    **Note:** The password that you specify here must be the same as the password for the encryption KeyStore password that you specified in step [5](#c) and the secret key password that you specified in step [6](#a).

8.   Start the server. 

Starting the server automatically encrypts the encryption.keystore password that you specified in the installed.properties file.

**Parent topic:** [Server settings and configuration](../topics/settings_ch.md)

