# Configuring the timeout value for SoftLayer clouds

To accommodate variations in responsiveness of the SoftLayer® cloud and to allow enough time for it to return resources to the blueprint designer, you can set a SoftLayer timeout value.

1.   On the computer that hosts the Heat engine, update the timeout value in the clouds\_user\_settings.conf file. This file is in the /usr/lib/heat/ibm-cloud-ext/resources/ folder. For the timeout value, provide the amount of time, in seconds, that the Heat engine waits for SoftLayer cloud to provide resource information. For the check\_create\_complete\_timeout value, provide the amount of time, in seconds, that the Heat engine waits for a virtual machine resource to complete. In the following example, the timeout value is set to 120 seconds, and the check\_create\_complete\_timeout is set to 300 seconds:

    ```
    [softlayer]
    client:
         {
            "timeout": 120
            "check_create_complete_timeout": 300
         }
    ```

2.   On the computer that hosts the cloud discovery service and the blueprint design server, create a configuration file. Use the following template for the file.

    ```
    [softlayer]
    client:
         {
            "timeout": 120
         }
    ```

    For the timeout variable, provide the amount of time, in seconds, that the cloud discovery service waits for the SoftLayer cloud to provide resource information. In the previous template, the timeout value is set to 120 seconds,

3.   Set the system variable CDS\_CLOUDS\_SETTINGS\_FILE to the location of the file. The file can be in any location on the system that hosts the cloud discovery service.
4.   In versions 6.2.1.1 and later that are installed on Red Hat Enterprise Linux™ version 7, provide the system variable to the cloud discovery service. In the Service section of the /usr/lib/systemd/system/ibm-cloud-discovery.service file, add an Environment parameter that defines the location of the system variable. The configuration file resembles the following code:

    ```
    [Unit]
    Description=IBM Cloud Discovery Service
    After=syslog.target network.target
    
    [Service]
    **Environment="CDS\_CLOUDS\_SETTINGS\_FILE=/usr/lib/heat/ibm-cloud-ext/resources/clouds\_user\_settings.conf"**
    Type=simple
    Restart=on-failure
    RestartSec=0
    ExecStart=/usr/bin/python -m clouddiscoveryservice.runserver
    
    [Install]
    WantedBy=network-online.target 
    ```

5.   Restart the cloud discovery service. See [Stopping the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.doc/topics/../../com.ibm.udeploy.install.doc/topics/stop_patterns.md) and [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.doc/topics/../../com.ibm.udeploy.install.doc/topics/start_patterns.md).
6.   Start the cloud discovery service. See [Starting the blueprint designer, cloud discovery service, and engine](../../com.ibm.udeploy.install.doc/topics/start_patterns.md).

**Parent topic:** [Connecting to the SoftLayer cloud](../../com.ibm.edt.doc/topics/cloud_connect_softlayer.md)

