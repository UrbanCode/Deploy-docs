# Converting a server to run as a Windows service

If you did not install the HCL® UrbanCode™ Deploy server to run as a Windows service, you can convert the server.

Stop the server.

1.   On a command line, run the following command as an administrator: 

    ```
    service.cmd install service\_name
    ```

    Use the name of the service for service\_name. To find the service name, open the service.cmd file in a text editor, and search for a line similar to this example: `set SERVICE_NAME=ibm-ucd`.

2.   Start the server. See [Starting and stopping the server](run_server.md#). 
3.   Start the Windows service. 

**Parent topic:** [Installing the server](../../com.udeploy.install.doc/topics/serverInstall.md)

