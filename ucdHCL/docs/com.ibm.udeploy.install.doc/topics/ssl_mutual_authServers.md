# Sharing secured properties among servers

To share applications that have secured properties among HCL® UrbanCode™ Deploy servers, exchange keys from each server's encryption keystore.

Make sure that the location of the Java™ keytool command is on the PATH variable of the servers. The keytool application is included in the Java developer kit and is not part of HCL UrbanCode Deploy.

To share applications that have secured properties, export the server's key and import it into each target server. This process enables applications from the exporting server to be used by the other servers. Repeat the process for each server with applications that you want to share.

1.   On the first server, open a command-line window, and go to the server installation conf/server directory. 
2.  Find the value of the encryption.keystore.alias property in the install/conf/server/installed.properties file. For example, the following code shows a value of `abcdkey1234`:

    ```
    encryption.keystore=../app_data/conf/encryption.keystore
    encryption.keystore.alias=abcdkey1234
    ```

    You must have this alias to complete the next steps.

3.   Go to the folder that contains the keystore file encryption.keystore. The default location is appData/conf/encryption.keystore, where appData is the application data folder.
4.  Run the following command to import the server key into a temporary keystore.You must enter this command on a single line.

    ```
    keytool -importkeystore -srckeystore encryption.keystore 
      -srcstorepass srcPassword 
      -srcstoretype jceks 
      -alias alias 
      -destkeystore temp.keystore 
      -deststorepass tempPassword 
      -deststoretype jceks
    ```

    -   For the srcPassword variable, specify the password for the server keystore. The default password is `changeit`.
    -   For the alias variable, specify the value of the encryption.keystore.alias property.
    -   For the tempPassword variable, specify a password for the temporary keystore. You will use this password later.
5.   Copy the temporary keystore, which is named temp.keystore in the previous example and store it in the appropriate folder on the second server. Check the **server.appdata.dir** property in the installed.properties file to determine where to store the keystore.
    -   If the **server.appdata.dir** property has a value of two periods \(..\), copy the keystore to the install/conf/ folder on the second server.
    -   If the property has a value other than two periods, the server uses an application data folder. Copy the keystore to the appdata/conf/ folder on the second server.
6.   On the second server, open a command-line window, and go to the server installation install/conf/server directory. 
7.  Run the following command to import the key in the temporary keystore into the server keystore.You must enter this command on a single line.

    ```
    keytool -importkeystore -srckeystore temp.keystore 
      -srcstorepass tempPassword 
      -srcstoretype jceks 
      -alias alias 
      -destkeystore encryption.keystore 
      -deststorepass destPassword 
      -deststoretype jceks
    ```

    -   For the tempPassword variable, specify the password for the temporary keystore.
    -   For the alias variable, specify the encryption.keystore.alias property of the first server, not the current server.
    -   For the destPassword password, specify the password for the current server keystore.
8.   Restart the second server. 
9.  Delete the temporary keystore file from each server.

The encryption key from the first server keystore is now on the second server keystore. As a result, the second server can now decrypt applications from the first server.

You can verify that the second server keystore has the key by running the following command on the second server:

```
keytool -list -keystore encryption.keystore 
  -storepass password 
  -storetype jceks
```

For the password variable, use the password of the server keystore.

This command lists the keys in the server keystore. If you copied the keys successfully, the list includes at least two keys: one from each of the servers. These keys are listed according to the encryption.keystore.alias properties of the respective servers. For example, the following output shows two keys:

```
Keystore type: jceks
Keystore provider: IBMJCE

Your keystore contains 2 entries

efghkey5678, Oct 15, 2013, SecretKeyEntry,
abcdkey1234, Nov 22, 2013, SecretKeyEntry,
```

Repeat this process to copy keys between other servers.

**Parent topic:** [SSL configuration](../../com.ibm.udeploy.doc/topics/SSLinstall.md)

