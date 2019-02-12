# Configuring SSL/TLS security for Chef

If your Chef server uses SSL/TLS security, you must import the Chef server key into the blueprint design server keystore.

On the blueprint design server, set the PATH system variable to include the location of the JRE or JDK on the system.

If the Chef server is configured with an IP address as the host name, the IP address must be in the subjectAltName field of the Chef server certificate. Contact the issuer of the Chef server SSL certificate for confirmation of whether the subjectAltName field is configured correctly.

The following script imports the Chef server key into the blueprint design server keystore. You can adapt this script to import the key for any remote system into the blueprint design server keystore.

1.   On the blueprint design server, create a script from the following template: 

    ```
    #!/bin/bash
    
    export DOMAIN_NAME=hostname
    
    # Retrieve the certificate from the remote service
    openssl s_client -connect $DOMAIN_NAME:443 -showcerts </dev/null\
     2>/dev/null | openssl x509 -outform PEM | tee ~/$DOMAIN_NAME.crt
    
    # Import the certificate into the JRE trust store.
    cd /opt/ibm-ucd-patterns/java/jre
    ./bin/keytool -import -trustcacerts -keystore ./lib/security/cacerts -storepass changeit\
     -noprompt -alias $DOMAIN_NAME -file ~/$DOMAIN_NAME.crt
    
    # Verify that the certificate was imported correctly.
    ./bin/keytool -list -trustcacerts -keystore ./lib/security/cacerts\
     -storepass changeit | grep $DOMAIN_NAME
    
    # Restart the service.
    /opt/ibm-ucd-patterns/bin/server stop
    /opt/ibm-ucd-patterns/bin/server start
    ```

2.   In the script, replace the variable `hostname` with the host name of the Chef server. 
3.   Update the line `cd /opt/ibm-ucd-patterns/java/jre` to point to the jre folder in the blueprint design server installation. 
4.   Update the final two lines of the script to stop and start the blueprint design server on your system. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md) and [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md).
5.   Run the script. 

**Parent topic:** [Integrating with Chef](../../com.edt.doc/topics/integrate_chef.md)

