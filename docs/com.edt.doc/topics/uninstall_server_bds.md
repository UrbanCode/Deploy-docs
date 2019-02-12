# Uninstalling the blueprint design server

To uninstall the blueprint design server, remove it from the Tomcat server.

1.   Stop the Tomcat service: 
    -   On Linux™, run the following command:

        ```
        server\_installation\_directory/bin/server stop
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is /opt/ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        /opt/ibm-ucd-patterns/bin/server stop
        ```

    -   On Windows™, run the following command:

        ```
        C:\server\_installation\_directory\bin\stop_server
        ```

        Use the location of the blueprint design server installation for `server\_installation\_directory`. The default installation directory is C:\\Program Files\\ibm-ucd-patterns. By default, the command looks like the following code:

        ```
        "C:\Program Files\ibm-ucd-patterns\bin\stop_server"
        ```

2.   Delete the contents of the following folder, including any subfolders: server\_installation\_directory/opt/tomcat/webapps/landscaper 
3.   Delete the following file, if it exists: server\_installation\_directory/opt/tomcat/webapps/landscaper.war 
4.   Uninstall the cloud discovery service: 
    -   On Red Hat Enterprise Linux version 7, run the following command:

        ```
        pip uninstall clouddiscoveryservice -y
        ```

    -   On Windows, run the following command:

        ```
        C:\python\_installation\_directory\python.exe -m pip uninstall clouddiscoveryservice -y
        ```

        Use the location where Python is installed for `python\_installation\_directory`. The default installation directory is C:\\Python27. By default, the command looks like this code:

        ```
        C:\Python27\python.exe -m pip uninstall clouddiscoveryservice -y
        ```

5.   If Tomcat is no longer needed on the system, you can uninstall Tomcat. 
6.   If Tomcat is still needed on the system, restart the Tomcat service: 

    ```
    service tomcat6 start
    ```

7.   If you are still using Tomcat, you might have to add your database driver back to Tomcat if you removed the driver in the earlier steps. 
8.   On the HCL® UrbanCode™ Deploy server, delete the following components: `ucd-agent-linux-ppc64`, `ucd-agent-linux-x86_64`, `ucd-agent-win-x86_64`, and `ucd-agent-linux-s390x`. 

**Parent topic:** [Uninstalling HCL UrbanCode Deploy](../../com.udeploy.install.doc/topics/uninstall_ch.md)

