# Configuring HTTPS security for OpenStack clouds

If your OpenStack server connects through HTTPS, you must import the OpenStack server key into the blueprint design server keystore.

The following script imports the OpenStack server key into the blueprint design server keystore. You can adapt this script to import the key for any remote system into the blueprint design server keystore.

1.   On the blueprint design server, create a script from the following template: 

    ```
    #!/bin/bash
    
    while getopts "s:p:l:h" opt; do
      case $opt in
        s)
          DOMAIN_NAME=$OPTARG
          ;;
        p)
          PORT=$OPTARG
          ;;
        l)
          UCD_P_HOME=$OPTARG
          ;;
        h)
          echo "Usage: ./import_os_cert.sh -s <OpenStack_HOSTNAME> -p <PORT> -l <UCDP_INSTALLED_PATH>"
          exit 0
          ;;
        \?)
          echo "Invalid option: -$OPTARG" >&2
          exit 1
          ;;
        :)
          echo "Option -$OPTARG requires an argument." >&2
          exit 1
          ;;
      esac
    done
    
    if [ -z "$DOMAIN_NAME" ]; then
        echo "Please set the OpenStack hostanme"
        exit 1
    fi
    
    if [ -z "$PORT" ]; then
        echo "Please set the OpenStack port"
        exit 1
    fi
    
    if [ -z "$UCD_P_HOME" ]; then
        echo "Please set the UCDP Installed Directory"
        exit 1
    fi
    
    
    # Retrieve the certificate from the remote service
    openssl s_client -connect $DOMAIN_NAME:$PORT -showcerts </dev/null\
     2>/dev/null | openssl x509 -outform PEM | tee ~/$DOMAIN_NAME.crt
    
    # Import the certificate into the JRE trust store.
    cd $UCD_P_HOME/java/jre
    ./bin/keytool -import -trustcacerts -keystore ./lib/security/cacerts -storepass changeit\
     -noprompt -alias $DOMAIN_NAME -file ~/$DOMAIN_NAME.crt
    
    # Verify that the certificate was imported correctly.
    ./bin/keytool -list -trustcacerts -keystore ./lib/security/cacerts\
     -storepass changeit | grep $DOMAIN_NAME
    
    # Restart the service.
    # $UCD_P_HOME/bin/server stop
    # $UCD_P_HOME/bin/server start
    ```

2.   Run the script. Use the following command:

    ```
    ./script\_name.sh -s OpenStack\_host -p port\_number -l blueprint\_desiger\_directory
    ```

    -   **`script\_name`**

        The name of the script that you created.

    -   **`port\_number`**

        The OpenStack communication port number.

    -   **`OpenStack\_host`**

        The host name of the OpenStack server that contains the key.

    -   **`blueprint\_desiger\_directory`**

        The name of the folder the blueprint designer is installed in. By default, the value of blueprint\_desiger\_directory is `/opt/ibm-ucd-patterns`.

3.   Restart the blueprint designer. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/stop_patterns.md#) and [Starting the blueprint designer, cloud discovery service, and engine](../../com.udeploy.install.doc/topics/start_patterns.md#).

**Parent topic:** [Connecting to OpenStack and OpenStack-based clouds](../../com.edt.doc/topics/cloud_connect_openstack.md)

