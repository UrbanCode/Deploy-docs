# Starting and stopping the server

To run the server, run the batch file or shell script for the server.

1.   Go to the server\_installation\\bin directory. The default server installation directory is /opt/ucd/server on Linux™ and C:\\Program Files\\ucd\\server on Windows™. 
2.   Run the run\_server.cmd batch file as an administrator \(Windows\), or `./server start` \(UNIX™ or Linux\). 
3.   On Linux systems that use `init.d`, you can run the server as a service by following these steps: 
    1.   Make sure that the file /etc/rc.d/init.d/functions has execute permissions. For example, you might run the following command:

        ```
        chmod ugo+x /etc/rc.d/init.d/functions
        ```

    2.   Copy the HCL® UrbanCode™ Deploy server initialization file to the /etc/init.d folder. The server initialization file is /installation\_location/server/bin/init/server, where installation\_location is the location that you installed the server. The default installation location is /opt/ucd/.
    3.   Make the /etc/init.d/server file executable. For example, you might run the following command:

        ```
        chmod +x /etc/init.d/server
        ```

    4.   Open the file /etc/init.d/server in a text editor and find the following lines of code: 

        ```
        SERVER_PROG="server"
        SERVER_HOME="/opt/ucd/server"
        SERVER_USER=@SERVER_USER@
        SERVER_GROUP=@SERVER_GROUP@
        ```

    5.   Replace `@SERVER_USER@` with the name of the user with which you run the server. 
    6.   Replace `@SERVER_GROUP@` with the name of the group with which you run the server. For example, if you run the server as the root user, use the following code:

        ```
        SERVER_PROG="server"
        SERVER_HOME="/opt/ucd/server"
        SERVER_USER="root"
        SERVER_GROUP="root"
        ```

    7.   Save the file. 
    8.   Install and configure the service with the following command: 

        ```
        chkconfig --add server
        ```

    9.   Test the service by running the following code: 

        ```
        service server start
        ```


To access the server, see [Accessing HCL UrbanCode Deploy](access_server.md). If the HCL UrbanCode Deploy server did not connect to the licence server, you see an error message that says that the server is unlicensed and cannot run deployments. To remove the error message, you must restore the connection to the license server and restart the HCL UrbanCode Deploy server.

To stop the server, return to the server\_installation\\bin directory. Run the stop\_server.cmd batch file as an administrator \(Windows\) or `./server stop` \(UNIX or Linux\).

When you run the server for the first time, you might see an error message that says that no agent or tag is configured to import new component versions. To import component versions, including built artifacts, you must use an agent, and the server requires that you specify a default agent for this purpose. You can override this default setting when you create a component. Follow these steps to specify a default agent or agent tag:

-   To specify a default agent, click **System** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent in the **Agent for Version Imports** list. Then, at the bottom of the page, click **Save**.
-   To specify a default agent tag, click **Settings** \> **System Settings** and under **General Settings**, clear the **Use Agent Tag For Integration** check box. Then, select an agent tag in the **Agent Tag for version imports** list. Then, at the bottom of the page, click **Save**. If no tags are listed, add a tag to one or more agents on the server.

**Parent topic:** [Starting HCL UrbanCode Deploy](../../com.ibm.udeploy.install.doc/topics/runProduct.md)

