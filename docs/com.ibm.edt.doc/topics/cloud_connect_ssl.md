# Configuring SSL security for OpenStack clouds

If your OpenStack cloud uses SSL security, you must import the security certificate into the blueprint design server keystore.

-   Install the blueprint design server.
-   Create a cloud connection as described in [Connecting to OpenStack and OpenStack-based clouds](cloud_connect_openstack.md).
-   On the blueprint design server, set the JAVA\_HOME system variable to the location of the JRE or JDK on the system.
-   On the blueprint design server, set the PATH system variable to include the location of the JRE or JDK on the system.

1.   On the blueprint design server, in a command prompt, go to the lib/security folder of the JRE or JDK, such as /opt/IBM/ibm-java-x86\_64-80/jre/lib/security. 
2.  Using the following command, download the certificate: 

    ```
    echo -n | openssl s_client -connect hostname:5000 | 
    sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' 
    > /tmp/mycert.crt
    ```

    **Note:** This command is split on multiple lines for clarity, but you must enter the command on a single line.

    Use the host name or IP address of the cloud system for `hostname`.

3.   Import the certificate into the blueprint design server keystore with the following command: 

    ```
    keytool -import -alias alias -file /tmp/mycert.crt 
    -keystore ./cacerts -storepass changeit -trustcacerts -noprompt
    ```

    **Note:** This command is split on multiple lines for clarity, but you must enter the command on a single line.

    Substitute a name for the cloud system for `alias`.

4.  Using the alias that you specified in the previous command, verify that the certificate was imported:

    ```
    keytool -list -keystore cacerts -storepass changeit | grep -i alias
    ```

    If you imported the certificate correctly, the command prints information about the certificate.


Now the blueprint design server can communicate with the OpenStack server.

**Parent topic:** [Connecting to OpenStack and OpenStack-based clouds](../../com.ibm.edt.doc/topics/cloud_connect_openstack.md)

